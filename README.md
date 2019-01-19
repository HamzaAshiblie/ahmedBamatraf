<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html dir="rtl">
   <head>
   <title>تقييم</title>
   <style>
		p.theresult ,.theresult-img{
		display:none;
		}
		
		input.calc {
		margin-right: 30px;
		}
		



   </style>
</head>
<body align='right' background="bg.jpg">
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

<script src="http://code.jquery.com/jquery-latest.min.js">
 </script>
<div align="right">
<div align="right">

<div class="container mt-5">
<h4>هل إتجاه الأرض جنوب شرق؟</h4>
<label class="radio-inline">
<input class="calc" type="radio" name="radio1" value="20" /> نعم
</label>

<label class="radio-inline">
<input class="calc" type="radio" name="radio1" value="0" /> لا
</label>
<hr>

<h4>هل الارض في احد افضل الاحياء في المدينة ؟</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio2" value="20" /> نعم
</label>
<label class="radio-inline">	
	<input class="calc" type="radio" name="radio2" value="10" /> نوعا ما
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio2" value="0" /> لا
</label>
<hr>

<h4>هل الخدمات الشخصية قريبة من الارض ( المدارس - العمل - الاهل - الخدمات ) ؟</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio3" value="10" /> نعم
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio3" value="0" /> لا
</label>
<hr>

<h4>هل الارض على شارعين او اكثر ؟</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio4" value="10" /> نعم
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio4" value="0" /> لا
</label>
<hr>

<h4>هل سعر الارض مناسبة ( يقاس بالارض المماثلة وليس بشكل خاص )</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio5" value="20" /> نعم
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio5" value="0" /> لا
</label>
<hr>

<h4>هل يوجد مسجد بالقرب من الارض ؟</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio6" value="10" /> نعم
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio6" value="0" /> لا
</label>
<hr>

<h4>هل هناك سهولة في دخول الحي والخروج منه ؟</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio7" value="10" /> نعم
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio7" value="5" /> نوعا ما يوجد صعوبة
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio7" value="0" /> لا
</label>
<hr>

<h4>عرض الشوارع المجاورة ؟</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio8" value="10" /> أكثر من 20
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio8" value="0" /> أقل من 20
</label>
<hr>

<h4>هل يوجد مركز تجاري قريب او محطة بترول ؟</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio9" value="0" /> نعم
</label>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio9" value="10" /> لا
</label>
<hr>

<h4>اطوال الارض :</h4>
<label class="radio-inline">
	<input class="calc" type="radio" name="radio10" value="10" /> مستطيلة
</label>
<label class="radio-inline">	
	<input class="calc" type="radio" name="radio10" value="5" /> مربعة
</label>
<label class="radio-inline">	
	<input class="calc" type="radio" name="radio10" value="0" /> شبه مربعة
</label>
<div>

<input type="text" name="sum" hidden/>
<p></p>


<a href="#show-result">
	<button type="button" class="show-result btn btn-primary">مشاهدة النتيجة</button>
</a>
<div class="theresult-img mt-3" ><img src="11.jpg" width='300px' /></div>

<p id="show-result" class="theresult alert" role='alert'>لم تقم بالتقييم بعد </p>

<script>

function calcscore(){
    var score = 0;
    $(".calc:checked").each(function(){
        score+=parseInt($(this).val(),10);
    });
    $("input[name=sum]").val(score)
    
	
	if(score <= 30){
		$("p.theresult").html("<p class='alert alert-danger' role='alert'  >إن كانت هدية فقط خذها</p>");
		}
	
	else if(score <= 59){
		$("p.theresult").html("<p class='alert alert-primary' role='alert' >مناسبة لعمل تجاري ( شالية مثلا ) 30</p>");
		}
		
	else if(score <= 60){
		$("p.theresult").html("<p class='alert alert-success' role='alert'>خذها  في حال الضرورة  او تميز السعر او ان  الحي راقي</p>");
		}
    else if(score <= 75){
		$("p.theresult").html("<p class='alert alert-primary' role='alert' >جيدة جداً</p>");
		}
	else if(score <= 90){
		$("p.theresult").html("<p class='alert alert-primary' role='alert' > توكل على الله </p>");
		}
	else if(score <= 110){
		$("p.theresult").html("<p class='alert alert-primary' role='alert' >رائعة</p>");
		}
	else if(score <= 130){
		$("p.theresult").html("<p class='alert alert-primary' role='alert' >خذها وانت مغمض</p>");
		}
	else{
		$("p.theresult").html("<p></p>");
		}

}

$().ready(function(){
    $(".calc").change(function(){
        calcscore()
    });

});

$(".show-result").click(function(){
 
  $("p.theresult").show();
   $(".theresult-img").show();
});

</script>

</div>
    </body>
</html>
