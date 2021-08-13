- ![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) `Note : this code use a google api !`


## Get minecrafr server infos with $_GET request named "ip" or "ip" and "port" if its a custom port 


```php

<?php
error_reporting(0);

if (empty($_GET["ip"])) {
  $ip = 'play.spartacube.fr';
} else {
$ip = $_GET["ip"];
}


if (empty($_GET["port"])) {
  $port = '25565';
} else {
$port = $_GET["port"];
}


$version = file_get_contents('http://api.serveurs-minecraft.com/api.php?Version_Ping&ip='.$ip.'&port='.$port.'');
$maxplayer = file_get_contents('http://api.serveurs-minecraft.com/api.php?Joueurs_Maximum_Ping&ip='.$ip.'&port='.$port.'');
$playeronline = file_get_contents('http://api.serveurs-minecraft.com/api.php?Joueurs_En_Ligne_Ping&ip='.$ip.'&port='.$port.'');
$MOTD = file_get_contents('http://api.serveurs-minecraft.com/api.php?Motd_Ping&ip='.$ip.'&port='.$port.'');
$favicon = file_get_contents('http://api.serveurs-minecraft.com/api.php?Favicon_Ping&ip='.$ip.'&port='.$port.'');

echo $version // Get version of the server
echo $maxplayer // Get slot(s) of the server
echo $playeronline  // Get player(s) online of the server
echo $MOTD // Get MOTD of the server
echo $favicon // Get favicon of the server
?>




## Live version here : https://arni.fr/mc/

