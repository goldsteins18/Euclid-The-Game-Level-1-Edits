---
layout: default
title: Level 1
cat: level
number: 1
---
<p id="goal">
	<b>Goal:</b> Construct an equilateral triangle such that the segment AB is one of its sides.
</p>

<script>
$(document).ready(function(){
  $("#button").click(function(){
    $("#answer").toggle();
  });
});
</script>
<p><span id="button"><b>Show answer &nbsp;</b></span> <span style="display:none" id="hint"> 1) Create a circle using point A as the center and point B as the edge. 2) Create a circle using point B as the center and point A as the edge. 3) Create a point where the two circles intersect (point C). 4) Connect point A to point C and point B to point C..</span></p>

<p id="winningimg">
<img src="data:image/png;base64, {% base64 img/Level1.png %}">
</p>

<div id="hidden" style="display: none">
<p id="level" onclick="location.href='/Level2/';" style="cursor:pointer;">
You unlocked a new tool: Constructing equilateral triangles! Go to <a href="/Level2/">level 2</a> !
</p>
</div>
<script type="text/javascript">
	{% include parameters480p.js %}
    parameters.customToolBar = "501 | 5 | 15 | 18 | 10"; //| 100001 | 100002 | 9 | 4 | 3 | 100003 | 53";
	parameters.ggbBase64 = "{% base64 ggb/Level1.ggb %}" ;
	parameters.language = "en"
	
</script>

<div id="applet_container">
</div>

<script type="text/javascript">
{% include testobjects.js %}
checkobject("pointtop",-0.4,0.3);
checkobject("pointbottom",-0.4,-0.3);
//checkobject("circleleft");
//checkobject("circleright");
checksegment("segmentLB",-1.1,0);
checksegment("segmentRB",0,0);
checksegment("segmentLT",-1.1,0);
checksegment("segmentRT",0,0);
	
if (drawn("pointtop") || drawn("pointbottom")) {  
	Command('progress = 33');
	}
if (drawn("segmentLT") || drawn("segmentLB") || drawn("segmentRB") ||  drawn("segmentRT")){
	Command('progress = 66');
   }
LevelCompleted((drawn("segmentLT") && drawn("segmentRT")) || (drawn("segmentLB") && drawn("segmentRB")),4);
}
</script>
