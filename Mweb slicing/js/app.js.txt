
var dataComplete_flag = false;
var LoginMethod = "id";
var demo = document.querySelector('#p');
var idLogin = document.querySelector('#idLogin');
var idLoginlabel = document.querySelector('#idLoginlabel');
var bioLogin = document.querySelector('#bioLogin');
var bioLoginlabel = document.querySelector('#bioLoginlabel');
var Loginbutton = document.querySelector('#Loginbutton');
var IDtextbox = document.querySelector('#IDtextbox');
var checkboxBefore = document.querySelector('#checkboxBefore');
var OTPCodeLabel1 = document.querySelector('#OTPCodeLabel1');
var OTPCodeLabel2 = document.querySelector('#OTPCodeLabel2');
var OTPCodeLabel3 = document.querySelector('#OTPCodeLabel3');
var OTPCodeLabel4 = document.querySelector('#OTPCodeLabel4');
var OTPCodeLabel5 = document.querySelector('#OTPCodeLabel5');
var OTPCodeLabel6 = document.querySelector('#OTPCodeLabel6');
var OTPcode = GenerateOTP();
var IDtypenumber = 0;
var Acctypenumber = 0;
var Pwdnumber = 0;
var IDNum = 0;
var AccountNum = 0;
var PasswordNum = 0;
var verifyNum = 0;
var RandomCodeList = [];
var switchbarL = new switchbarL();
var switchbarR = new switchbarR();
var biointerface = new biointerface();
var moveDistance = 0;
var flag = 0;
var container = document.querySelector('.container');
var biointerface = document.querySelector('#biointerface');
var IDinterface = document.querySelector('#IDinterface');
  



function switchbarL () {

  var animationStartTime = 0;
  var animationDuration = 50;
  var target = document.querySelector('#switchbarL');

  this.startAnimation = function() {
  	//demo.innerHTML = LoginMethod;
    animationStartTime = Date.now();
    requestAnimationFrame(update);
  };

  function update() {
  	var moveDistance = 0;
    var currentTime = Date.now();
    var positionInAnimation = (currentTime - animationStartTime) / animationDuration;
    var xPosition = positionInAnimation * 150;
    moveDistance += xPosition;
    target.style.transform = 'translate(' + xPosition + 'px)';


    if (positionInAnimation <= 1)
      requestAnimationFrame(update);
    else{
  	  var advalue = 188-moveDistance;
  	  target.style.left = advalue+"px";
  	  var moveDistance = 0;
    }
  }
}



function switchbarR () {

  var animationStartTime = 0;
  var animationDuration = 50;
  var target = document.querySelector('#switchbarR');

  this.startAnimation = function() {
  	//demo.innerHTML = LoginMethod;
    animationStartTime = Date.now();
    requestAnimationFrame(update);
  };

  function update() {
  	var moveDistance = 0;
    var currentTime = Date.now();
    var positionInAnimation = (currentTime - animationStartTime) / animationDuration;
    var xPosition = positionInAnimation * -150;
    moveDistance += xPosition;
    target.style.transform = 'translate(' + xPosition + 'px)';


    if (positionInAnimation <= 1)
      requestAnimationFrame(update);
    else{
  	  var advalue = -130-moveDistance;
  	  target.style.left = advalue+"px";
  	  var moveDistance = 0;
    }
  }
}

function biointerface () {

  var animationStartTime = 0;
  var animationDuration = 50;
  var target = document.querySelector('#biointerface');

  this.startAnimation = function() {
  	//demo.innerHTML = LoginMethod;
    animationStartTime = Date.now();
    requestAnimationFrame(update);
  };

  function update() {
  	var moveDistance = 0;
    var currentTime = Date.now();
    var positionInAnimation = (currentTime - animationStartTime) / animationDuration;
    var xPosition = positionInAnimation * 0;
    moveDistance += xPosition;
    target.style.transform = 'translate(' + xPosition + 'px)';


    if (positionInAnimation <= 1)
      requestAnimationFrame(update);
    else{
  	  var advalue =0;
  	  target.style.left = advalue+"px";
  	  var moveDistance = 0;
    }
  }
}


function GenerateOTP(){

	OTPCode = "";
    OTPCodeLabel1.innerHTML = Math.floor(Math.random() * 10);
    OTPCodeLabel2.innerHTML = Math.floor(Math.random() * 10);
    OTPCodeLabel3.innerHTML = Math.floor(Math.random() * 10);
    OTPCodeLabel4.innerHTML = Math.floor(Math.random() * 10);
    OTPCodeLabel5.innerHTML = Math.floor(Math.random() * 10);
    OTPCodeLabel6.innerHTML = Math.floor(Math.random() * 10);
    OTPCode = OTPCodeLabel1.innerHTML+OTPCodeLabel2.innerHTML + OTPCodeLabel3.innerHTML + OTPCodeLabel4.innerHTML + OTPCodeLabel5.innerHTML + OTPCodeLabel6.innerHTML;
    demo.innerHTML = OTPCode;
    return OTPCode;

}





//輸入資料檢核

document.querySelector('#IDtextbox').addEventListener("input", (e) =>{
	IDNum = document.querySelector('#IDtextbox').value.length;
	if (IDNum && AccountNum && PasswordNum && verifyNum > 3){
		Loginbutton.style['background-color'] = "rgb(234, 47, 68)";
		dataComplete_flag = true;
	}
	else{
		Loginbutton.style['background-color'] = "rgb(204, 204, 204)";
	}
	if (IDNum == 0){
		dataComplete_flag = false;
	}
	demo.innerHTML = IDNum;
 });


document.querySelector('#Accounttextbox').addEventListener("input", (e) =>{
	AccountNum = document.querySelector('#Accounttextbox').value.length;
	if (IDNum && AccountNum && PasswordNum && verifyNum > 3){
		Loginbutton.style['background-color'] = "rgb(234, 47, 68)";
		dataComplete_flag = true;
	}
	else{
		Loginbutton.style['background-color'] = "rgb(204, 204, 204)";
	}
	if (AccountNum == 0){
		dataComplete_flag = false;
	}
	demo.innerHTML = IDNum;
 });

document.querySelector('#Passwordtextbox').addEventListener("input", (e) =>{
	PasswordNum = document.querySelector('#Passwordtextbox').value.length;
	if (IDNum && AccountNum && PasswordNum && verifyNum > 3){
		Loginbutton.style['background-color'] = "rgb(234, 47, 68)";
		dataComplete_flag = true;
	}
	else{
		Loginbutton.style['background-color'] = "rgb(204, 204, 204)";
	}
	if (PasswordNum == 0){
		dataComplete_flag = false;
	}
	demo.innerHTML = IDNum;
 });

document.querySelector('#verifyInput').addEventListener("input", (e) =>{
	verifyNum = document.querySelector('#verifyInput').value.length;
	if (IDNum && AccountNum && PasswordNum && verifyNum > 3){
		Loginbutton.style['background-color'] = "rgb(234, 47, 68)";
		dataComplete_flag = true;
	}
	else{
		Loginbutton.style['background-color'] = "rgb(204, 204, 204)";
	}
	if (verifyNum < 2){
		dataComplete_flag = false;
	}
	demo.innerHTML = IDNum;
 });




//事件
//點選帳號登入
document.querySelector('#idLogin').addEventListener('click', (e) => {


  IDinterface.style.transform =
    "translateX(" + 0+ "px)";
  biointerface.style.transform =
    "translateX(" + 0 + "px)";

  if(LoginMethod == "bio"){
    if(flag <2){
    idLoginlabel.style.color = "rgb(255, 255, 255)";
    bioLoginlabel.style.color = "rgb(255, 84, 103)";
    switchbarR.startAnimation();
    document.querySelector('#switchbarR').style['background-color'] = "rgb(234, 47, 68)";
    document.querySelector('#switchbarR').style.display = "block";
    document.querySelector('#switchbarL').style.display = "none";
    flag++;
    }
    if(flag >=2){
      document.querySelector('#switchbarR').style.display = "block";
      document.querySelector('#switchbarL').style.display = "none";
      switchbarR.startAnimation();
      idLoginlabel.style.color = "rgb(255, 255, 255)";
      bioLoginlabel.style.color = "rgb(255, 84, 103)";
    }
    LoginMethod = "id";
  }
  

});


//點選快速登入

document.querySelector('#bioLogin').addEventListener('click', (e) => {

  biointerface.style.transform =
    "translateX(-" + 375 + "px)";
  IDinterface.style.transform =
    "translateX(-" + 375 + "px)";


  if(LoginMethod == "id"){
    if(flag<2){
    bioLoginlabel.style.color = "rgb(255, 255, 255)";
    idLoginlabel.style.color = "rgb(255, 84, 103)";
    switchbarL.startAnimation();
    document.querySelector('#switchbarR').style['background-color'] = "rgb(234, 47, 68)";
    document.querySelector('#switchbarR').style.display = "block";
    document.querySelector('#switchbarL').style.display = "none";
    flag++;
    }
    if (flag>=2){
        bioLoginlabel.style.color = "rgb(255, 255, 255)";
      idLoginlabel.style.color = "rgb(255, 84, 103)";
      switchbarL.startAnimation();
      document.querySelector('#switchbarL').style['background-color'] = "rgb(234, 47, 68)";
      document.querySelector('#switchbarR').style.display = "none";
      document.querySelector('#switchbarL').style.display = "block";
      demo.innerHTML = flag;
    }
    LoginMethod = "bio";
  }
  


  biointerface.startAnimation();
  document.querySelector('#biointerface').style.display = "block";

});


//點選還沒有帳戶
document.querySelector('#noAccountbutton').addEventListener('click', (e) => {
	window.location.href='https://dawho.tw/how/apply/';

});

document.querySelector('#OTPrefreshimg').addEventListener('click', (e) => {
	OTPCode = GenerateOTP();
});

document.querySelector('#startButton').addEventListener('click', (e) => {
    biointerface.style.transform =
    "translateX(-" + 750 + "px)";
});

//檢核機制


document.querySelector('#Loginbutton').addEventListener("click", (e) =>{
	if (dataComplete_flag == true){
		var alertMessage = ""
		if(verifyInput.value != OTPCode){
			alertMessage += "驗證碼錯誤\n";
		}
		if(Accounttextbox.value.length<6 || Accounttextbox.value.length>20){
			alertMessage += "使用者代碼-最少6碼-最多20碼\n";
		}
		if(Passwordtextbox.value.length<6 || Passwordtextbox.value.length>20){
			alertMessage += "網路密碼-最少6碼-最多20碼";
		}
		if(alertMessage.length != 0){
			alert(alertMessage);
		}
		else{
			if(IDtextbox.value != 'A128455942'){
				alert("查無此會員");
			}
			else if(Accounttextbox.value != 'a12345'){
				alert("使用者代碼錯誤");
			}
			else if(Passwordtextbox.value != 'b12345'){
				alert("網路密碼錯誤");
			}
			else{
				alert("登入成功");
			}
		}

		
	}
  
 });






