+++
title="Block time simulation"
+++

<div>
<iframe name="game" src="/blocktime-demo/main.html?network=100&blocktime=10" width="330" height="360"></iframe>
</div>
<div>
Block time
</br>
<input type="range" min="0" max="2000" value="10" id="blocktime" name="blocktime" oninput="this.nextElementSibling.value = this.value">
<output name="blocktimeDisplay">10</output> ms
</div>
<div>
Network propagation time
</br>
<input type="range" min="0" max="2000" value="100" id="network" name="network" oninput="this.nextElementSibling.value = this.value">
<output name="networkDisplay">100</output> ms
</div>
<div>
    <button type="button" onclick="var bts=document.getElementsByName('blocktime')[0]; bts.value=10; var nds=document.getElementsByName('network')[0]; nds.value=100; btd=document.getElementsByName('blocktimeDisplay')[0]; btd.value=10; ntd=document.getElementsByName('networkDisplay')[0]; ntd.value=100;">Reset</button>
    <button type="button" onclick="var ifr=document.getElementsByName('game')[0]; var bts=document.getElementsByName('blocktime')[0]; var nds=document.getElementsByName('network')[0]; ifr.src='/blocktime-demo/main.html?network='+nds.value+'&blocktime='+bts.value;">Apply</button>
</div>
