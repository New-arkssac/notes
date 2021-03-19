# 第十四关
# Pass-014

直接查看源码
```php
function getReailFileType($filename){
    $file = fopen($filename, "rb");
    $bin = fread($file, 2); //只读2字节
    fclose($file);
    $strInfo = @unpack("C2chars", $bin);    
    $typeCode = intval($strInfo['chars1'].$strInfo['chars2']);    
    $fileType = '';    
    switch($typeCode){      
        case 255216:            
            $fileType = 'jpg';
            break;
        case 13780:            
            $fileType = 'png';
            break;        
        case 7173:            
            $fileType = 'gif';
            break;
        default:            
            $fileType = 'unknown';
        }    
        return $fileType;
}

$is_upload = false;
$msg = null;
if(isset($_POST['submit'])){
    $temp_file = $_FILES['upload_file']['tmp_name'];
    $file_type = getReailFileType($temp_file);

    if($file_type == 'unknown'){
        $msg = "文件未知，上传失败！";
    }else{
        $img_path = UPLOAD_PATH."/".rand(10, 99).date("YmdHis").".".$file_type;
        if(move_uploaded_file($temp_file,$img_path)){
            $is_upload = true;
        } else {
            $msg = "上传出错！";
        }
    }
}
```
代码的大致意思是通过读取前两个字节来判断是什么类型的文件

可以用图片码来绕过
直接用bp抓包然后在上传的图片内容中添加
GIF89a的图片声明
然后使用文件包含去包含图片码执行
![image](./images/image52.png)
![image](./images/image53.png)
![image](./images/image54.png)

过关～～:D
PS:这一关不想需要更换后缀名，可以直接使用php后缀，因为它是看文件的前两个字节的图片声明，而不是去检查后缀名

