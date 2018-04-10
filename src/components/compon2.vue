<template>
  <div class="info">
    <h1>技术栈</h1>
    <div class="socialAnimationWrapper">
	<ul class="socialAnimation">
		<li class="person"><img src="person.png" alt=""/></li>
		<li class="facebook">
			<div class="containerImg"></div>
			<div class="connector">
				<span class="one"></span>
				<span class="two"></span>
			</div>
		</li>
		<li class="googlePlus">
			<div class="containerImg"></div>
			<div class="connector">
				<span class="one"></span>
				<span class="two"></span>
			</div>
		</li>
		<li class="twitter">
			<div class="containerImg"></div>
			<div class="connector">
				<span class="one"></span>
				<span class="two"></span>
			</div>
		</li>
		<li class="linkedin">
			<div class="containerImg"></div>
			<div class="connector">
				<span class="one"></span>
				<span class="two"></span>
			</div>
		</li>
		<li class="yt">
			<div class="containerImg"></div>
			<div class="connector">
				<span class="one"></span>
				<span class="two"></span>
			</div>
		</li>
	</ul>
</div>
  </div>
</template>
<style lang="less" scoped>
.socialAnimation{
    width: 400px;
    height: 300px;
    margin: 20px auto;
}
.socialAnimation li{
    position: absolute;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    border-radius: 50%;
    border: 1px solid #fff;
    list-style-type: none;
    -webkit-animation: scaleLi 4s ease-in-out infinite;
    -moz-animation: scaleLi 4s ease-in-out infinite;
    -o-animation: scaleLi 4s ease-in-out infinite;
    -ms-animation: scaleLi 4s ease-in-out infinite;
    animation: scaleLi 4s ease-in-out infinite;
}
@-webkit-keyframes scaleLi {
    0% { 
        -webkit-transform: scale(1);
    }
    45% { 
        -webkit-transform: scale(1);
    }
    60% {
        -webkit-transform: scale(1.2);
    }
    75% { 
        -webkit-transform: scale(1);
    }
    100% { 
        -webkit-transform: scale(1);
    }
}
@-moz-keyframes scaleLi {
    0% { 
        -moz-transform: scale(1);
    }
    45% { 
        -moz-transform: scale(1);
    }
    60% {
        -moz-transform: scale(1.2);
    }
    75% { 
        -moz-transform: scale(1);
    }
    100% { 
        -moz-transform: scale(1);
    }
}
@-o-keyframes scaleLi {
    0% { 
        -o-transform: scale(1);
    }
    45% { 
        -o-transform: scale(1);
    }
    60% {
        -o-transform: scale(1.2);
    }
    75% { 
        -o-transform: scale(1);
    }
    100% { 
        -o-transform: scale(1);
    }
}
@-ms-keyframes scaleLi {
    0% { 
        -ms-transform: scale(1);
    }
    45% { 
        -ms-transform: scale(1);
    }
    60% {
        -ms-transform: scale(1.2);
    }
    75% { 
        -ms-transform: scale(1);
    }
    100% { 
        -ms-transform: scale(1);
    }
}
@keyframes scaleLi {
    0% { 
        transform: scale(1);
    }
    45% { 
        transform: scale(1);
    }
    60% {
        transform: scale(1.2);
    }
    75% { 
        transform: scale(1);
    }
    100% { 
        transform: scale(1);
    }
}

.socialAnimation .person{
    width: 80px;
    height: 80px;
    margin: 110px 0 0 160px;
    z-index: 9;
}
.socialAnimation .person img{
    width: 70px;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    border-radius: 50%;
    margin: 5px;
    background-color: #fff;
}

.socialAnimation li div.connector{
    position: absolute;
    background-color: #fff;
    height: 5px;
}
.socialAnimation li div.connector span{
    display: block;
    width: 15px;
    height: 15px;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    border-radius: 50%;
    background-color: #fff;
    margin: -5px 0 0 0;
    position: absolute;
    -webkit-animation: connections 4s ease-in-out infinite;
    -moz-animation: connections 4s ease-in-out infinite;
    -o-animation: connections 4s ease-in-out infinite;
    -ms-animation: connections 4s ease-in-out infinite;
    animation: connections 4s ease-in-out infinite;

}
.socialAnimation li div.connector span.two{
    -webkit-animation: connections 4s ease-in-out infinite 1s;
    -moz-animation: connections 4s ease-in-out infinite;
    -o-animation: connections 4s ease-in-out infinite;
    -ms-animation: connections 4s ease-in-out infinite;
    animation: connections 4s ease-in-out infinite 1s;
}

@-webkit-keyframes connections {
    0% { left: 0}
    80% { left: 100%; }
}
@-moz-keyframes connections {
    0% { left: 0}
    80% { left: 100%; }
}
@-o-keyframes connections {
    0% { left: 0}
    80% { left: 100%; }
}
@-ms-keyframes connections {
    0% { left: 0}
    80% { left: 100%; }
}
@keyframes connections {
    0% { left: 0}
    80% { left: 100%; }
}

.socialAnimation li .containerImg{
    position: absolute;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    border-radius: 50%;
    background-color: #fff;
    -webkit-transition: background 0.3s linear;
    -moz-transition: background 0.3s linear;
    -o-transition: background 0.3s linear;
    -ms-transition: background 0.3s linear;
    transition: background 0.3s linear;
    z-index: 10;
    background-repeat: no-repeat;
}

.socialAnimation .facebook{
    width: 90px;
    height: 90px;
}
.socialAnimation .facebook .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/facebookIcon.png");
}
.socialAnimation .facebook:hover .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/facebookIconHover.png");
}
.socialAnimation .facebook .containerImg{
    width: 80px;
    height: 80px;
    margin: 5px;
}
.socialAnimation .facebook div.connector{
    position: absolute;
    background-color: #fff;
    height: 5px;
    width: 150px;
    margin: 105px 0 0 65px;

    transform:rotate(-115deg); 
    -webkit-transform:rotate(-145deg); 
    -moz-transform:rotate(-135deg); 
    -ms-transform:rotate(-135deg); 
    -o-transform:rotate(-115deg); 

}


.socialAnimation .googlePlus{
    width: 85px;
    height: 85px;
    margin: 20px 0 0 240px;
}
.socialAnimation .googlePlus .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/googlePlusIcon.png");
}
.socialAnimation .googlePlus:hover .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/googlePlusIconHover.png");
}
.socialAnimation .googlePlus .containerImg{
    width: 75px;
    height: 75px;
    margin: 5px;
}
.socialAnimation .googlePlus div.connector{
    position: absolute;
    background-color: #fff;
    height: 5px;
    width: 70px;
    margin: 90px 0 0 -35px;

    transform:rotate(-45deg); 
    -webkit-transform:rotate(-45deg); 
    -moz-transform:rotate(-45deg); 
    -ms-transform:rotate(-45deg); 
    -o-transform:rotate(-45deg); 

}

.socialAnimation .twitter{
    width: 60px;
    height: 60px;
    margin: 120px 0 0 300px;
}
.socialAnimation .twitter .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/twitterIcon.png");
}
.socialAnimation .twitter:hover .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/twitterIconHover.png");
}
.socialAnimation .twitter .containerImg{
    width: 50px;
    height: 50px;
    margin: 5px;
}
.socialAnimation .twitter div.connector{
    position: absolute;
    background-color: #fff;
    height: 5px;
    width: 90px;
    margin: 25px 0 0 -85px;

    transform:rotate(0deg); 
    -webkit-transform:rotate(0deg); 
    -moz-transform:rotate(0deg); 
    -ms-transform:rotate(0deg); 
    -o-transform:rotate(0deg); 

}

.socialAnimation .linkedin{
    width: 50px;
    height: 50px;
    margin: 150px 0 0 40px;
}
.socialAnimation .linkedin .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/linkedInIcon.png");
}
.socialAnimation .linkedin:hover .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/linkedInIconHover.png");
}
.socialAnimation .linkedin .containerImg{
    width: 40px;
    height: 40px;
    margin: 5px;
}
.socialAnimation .linkedin div.connector{
    position: absolute;
    background-color: #fff;
    height: 5px;
    width: 150px;
    margin: 8px 0 0 25px;

    transform:rotate(-190deg); 
    -webkit-transform:rotate(-190deg); 
    -moz-transform:rotate(-190deg); 
    -ms-transform:rotate(-190deg); 
    -o-transform:rotate(-190deg); 

}

.socialAnimation .yt{
    width: 80px;
    height: 80px;
    margin: 210px 0 0 150px;
}
.socialAnimation .yt .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/ytIcon.png");
}
.socialAnimation .yt:hover .containerImg{
    background-image: url("http://szymondziewonski.com/pictures/website/ytIconHover.png");
}
.socialAnimation .yt .containerImg{
    width: 70px;
    height: 70px;
    margin: 5px;
}
.socialAnimation .yt div.connector{
    position: absolute;
    background-color: #fff;
    height: 5px;
    width: 80px;
    margin: -5px 0 0 5px;

    transform:rotate(100deg); 
    -webkit-transform:rotate(100deg); 
    -moz-transform:rotate(100deg); 
    -ms-transform:rotate(100deg); 
    -o-transform:rotate(100deg); 

}
</style>

