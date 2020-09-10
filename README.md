window.onload = function() {
	lengthObj = document.getElementById('txtLength');
	widthObj = document.getElementById('txtWidth');
	heightObj = document.getElementById('txtHeight');
	costObj = document.getElementById('tdCost');
	document.getElementById('btnReset').onclick = resetInputs;
	document.getElementById('btnCalcCost').onclick = Cost;
}

function resetInputs() {
     lengthObj.value = '';
     widthObj.value = '';
     heightObj.value = '';
     costObj.innerHTML = '';
}

function SurfaceArea() {
	var length = new Number(lengthObj.value);
    var width = new Number(widthObj.value);
	var height = new Number(heightObj.value);
    if(isNaN(length) || isNaN(width) || isNaN(height)) {
		alert('Invalid length or width or height');
		return;
	}
    return (length*width*2) + (length*height*2) + (width*height*2);
}

function Edges() {
	var length = new Number(lengthObj.value);
	var width = new Number(widthObj.value);
	var height = new Number(heightObj.value);
	return (length*2) + (height*4) + (width*2);
	}

function Glue() {
	var edges = Edges();
	return edges*0.1;
}

function Labour() {
	var sa = SurfaceArea();
	return sa*(60/6000);
}

function Cost() {
	var height = new Number(heightObj.value);
	var GlassCost;
	if (height < 26) {
		GlassCost = 0.06;
	}
	else {
		GlassCost = 0.1;
	}
	var sa = SurfaceArea();
	var g = Glue();
	var l = Labour();
	var Glass = sa * GlassCost;
	var number = l + g + Glass + (0.1 * l + g + Glass); 
	var money = number.toFixed(2); 
	costObj.innerHTML = "";
	costObj.innerHTML = "$" + money;
}
