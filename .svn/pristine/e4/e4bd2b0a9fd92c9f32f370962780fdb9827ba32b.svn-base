function carousel(id,interval,speed) {
	//得到所有元素
	var $carousel = $(id);
	var $imageListLis = $carousel.find(".imageList li");
	var $leftBtn = $carousel.find(".leftBtn");
	var $rightBtn = $carousel.find(".rightBtn");
	var $circles = $carousel.find(".circleList li");
	var imageAmount = $imageListLis.length;
		
	var nowimg = 0;

	$rightBtn.click(rightBtnFunc);	
	function rightBtnFunc(){
		if(!$imageListLis.is(":animated")){
			
			nowimg ++;
			if(nowimg > imageAmount - 1){
				nowimg = 0;
			}
			
			changePictureAndChangeCircles();
		}
	}	
	$leftBtn.click(function(){
		if(!$imageListLis.is(":animated")){
			
			nowimg --;
			if(nowimg < 0){
				nowimg = imageAmount - 1;
			}
			
			changePictureAndChangeCircles();
		}
	});

	$circles.click(function(){
		nowimg = $(this).index();
		changePictureAndChangeCircles();
	});

	function changePictureAndChangeCircles(){
		
		$imageListLis.stop(true).fadeOut(speed);
		// 
		$imageListLis.eq(nowimg).stop(true).fadeIn(speed);
		
		$circles.eq(nowimg).addClass("cur").siblings().removeClass("cur");
	}

	var timer = setInterval(rightBtnFunc,interval);

	$carousel.mouseenter(function() {
		clearInterval(timer);
	});

	$carousel.mouseleave(function() {
		clearInterval(timer);
		timer = setInterval(rightBtnFunc,interval);
	});
}