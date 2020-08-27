window.onload = function() {
	lengthObj = document.getElementById('txtLength');
	widthObj = document.getElementById('txtWidth');
	heightObj = document.getElementById('txtHeight');
	SurfaceAreaObj = document.getElementById('tdCost');
	document.getElementById('btnReset').onclick = resetInputs;
	document.getElementById('btnCalcCost').onclick = SurfaceArea;
}

function resetInputs() {
     lengthObj.value = '';
     widthObj.value = '';
     heightObj.value = '';
     SurfaceAreaObj.innerHTML = '';
}

function SurfaceArea() {
	var length = new Number(lengthObj.value);
    var width = new Number(widthObj.value);
	var height = new Number(heightObj.value);
    SurfaceArea.innerHTML = '';
    if(isNaN(length) || isNaN(width) || isNaN(height)) {
         alert('Invalid length or width or height');
         return;
	}
    SurfaceAreaObj.innerHTML = (length*width*2) + (length*height*2) + (width*height*2);
}
function Edges() {
	var length = new Number(lengthObj.value);
	var width = new Number(widthObj.value);
	var height = new Number(heightObj.value);
	(length*width*2) + (length*height*2) + (width*height*2);
	}

