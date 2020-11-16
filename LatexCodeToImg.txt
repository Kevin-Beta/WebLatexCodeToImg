let suckIt = `
<div style="position: fixed;top: 50%;z-index: 999;right: 10%;padding: 1em;background: rgba(233,233,233,.6);border: 1px solid #aaa;">

	公式图像:(转换时间1~3秒)
	<br>
	<img src="http://latex.codecogs.com/gif.latex?x+y=z" id="img" />
	<br>
	<textarea placeholder="LatexCode" id="code" style="padding: 10px;height: 20px;width: 200px;margin: 10px;">x+y=z</textarea>
	
	<p style="text-align: center;">
		<input type="submit" value="Convert" onclick="convert();" style="border: 1px solid #aaa;padding: 5px;color: #999;cursor: pointer;">
	</p>
</div>
`;

document.body.insertAdjacentHTML("afterbegin", suckIt);

function convert() {
    let code = document.getElementById('code').value || 'x+y=z';
	let fuck = setInterval(() => {
		let url="http://latex.codecogs.com/gif.latex?"+code;
		document.getElementById('img').src=url;
		window.clearInterval(fuck);
	}, 10);
}