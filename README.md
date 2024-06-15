<br clear="both">

<div align="center">
  <img height="432" width="768" src="https://user-images.githubusercontent.com/74038190/225813708-98b745f2-7d22-48cf-9150-083f1b00d6c9.gif"  />
</div>
<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Arial+Code&size=55&pause=500&color=7b68ee&center=true&random=false&width=1000&height=100&lines=-- xolop --&duration=3500" alt="Typing SVG" /></a>
<div align="center">
  
**`scripts? cheats? autobot? crypto? telebot? - I will do!`**
</div>
<h2 align="center">Socials</h2>

<div align="center">
  <a href="https://t.me/xolopdev" target="_blank">

  ![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)
  </a>
    <a href="https://github.com/o-xolop-o" target="_blank">
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
  </a>
</div>


<div align="center">

[<img src="./resources/pixeltap.png" width="144"/>](https://t.me/pixelversexyzbot?start=1132612218)

  <h1 align="center">Автокликер для игры PixelTap</h1>
  
  <p align="center">
    <strong>Данный бот предназначен для автоматизации боев в игре</strong>
  </p>
  <img height="400" src="./resources/pixel.gif"/>
  
  <img height="400" src="./resources/2.png"/>

</div>

## Установка скрипта

1. Откройте Telegram Web в любом браузере, перейдите в бота <a href="https://t.me/pixelversexyzbot?start=1132612218">PixelTap</a> и запустите мини-игру

2. Нажмите ПКМ в любую **область мини-игры** и нажмите исследовать элемент
3. В открывшейся области нажмите на вкладку "Консоль" 
4. В конце всего текста в этой вкладке после знака "**>**" вставьте скрипт, предоставленный ниже
5. Запустите бой
6. Кликните в область со скриптом и нажмите **Enter**

```JavaScript
const consoleStyles = {
  red: 'font-weight: bold; color: red;',
  green: 'font-weight: bold; color: green;',
  white: 'font-weight: bold; color: white;',
  black: 'font-weight: bold; color: black;',
  yellow: 'font-weight: bold; color: yellow;',
  prefix: '%c ╰┈➤ '
};
const originalConsoleLog = console.log;
console.log = function (...args) {
  if (args[0].includes('╰┈➤') || args[0].includes('github.com')){
    originalConsoleLog.apply(console, args)
}};

console.clear();
console.log(`${consoleStyles.prefix}🚀 Loading...`, consoleStyles.green);
 
const sleep = ms => new Promise(resolve => setTimeout(resolve, ms));

const stats = {
  victories: 0,
  defeats: 0,
  totalCoins: 0
};

let isBattle, isFinish = false;
 
const checkState = async () => {
    try {
        if (document.querySelector('._userAvatar_1cwmg_18')) {
            return await sleep(10), await checkState();

        } else if (document.querySelector('._searchBattle_lmtrw_1')) {
            return await sleep(1000), await checkState();

        } else if (document.querySelector('._battle_9aqc0_1') && !isBattle) {
            return isBattle = true, await playBattle();

        } else if (document.querySelector('._resultContainer_bgfdy_1') && isFinish) {
            const playBtn = document.querySelector('#root button._button_fe4eh_1._purple_fe4eh_31._textUppercase_fe4eh_28');
            const finishCoinsText = document.querySelector('#root ._reward_bgfdy_17 > span')?.innerText || '';
            const isVictory = !finishCoinsText.includes('-');

            if (isVictory) {
              stats.victories++;
            }
            else {
              stats.defeats++;
            }

            const currentTime = new Date();
            const timeString = currentTime.toLocaleString('ru-RU', {
              day: '2-digit',
              month: '2-digit',
              hour: '2-digit',
              minute: '2-digit',
              second: '2-digit',
            }).replace(',', '');

            function getConsoleTextColor() {
              const isDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
              return isDarkMode ? consoleStyles.white : consoleStyles.black;
            }
            
            stats.totalCoins += parseInt(finishCoinsText.replace(/[^\d-]/g, ''), 10);
            
            console.group(`[${timeString}] Game Result`);
            console.log(`${consoleStyles.prefix}${isVictory ? '🎉 Victory' : '💀 Defeat'} (${finishCoinsText})`,isVictory ? consoleStyles.green : consoleStyles.red);
            console.log(`${consoleStyles.prefix}${stats.victories} W | ${stats.defeats} L | ${stats.totalCoins >= 0 ? '+' : ''}${stats.totalCoins.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')}`, getConsoleTextColor());
            console.groupEnd();            
            
            if (playBtn) return (isFinish = false, await sleep(2000), playBtn.click(), await sleep(1000), await checkState());
        }
    } catch (e) { return await sleep(Math.floor(Math.random() * 65) + 1003), await checkState(); }
};
 
const playBattle = async () => {
    const clickableArea = document.querySelector('.clickableArea');
    if (clickableArea) { for (let i = 0; i < 12; i++) { clickableArea.click(); await sleep(Math.floor(Math.random() * 11) + 7) }
    } else if (document.querySelectorAll('._card_1ymyk_1').length) { document.querySelectorAll('._card_1ymyk_1')[Math.floor(Math.random() * 4)].click() } else { if (!document.querySelector('._battle_9aqc0_1')) return isBattle = false, isFinish = true, await checkState() }
    return await sleep(1000), await playBattle();
};
 
document.addEventListener('click', function() { if (!isBattle) { checkState() }});

const script2ByLabel = document.createElement('div');
script2ByLabel.textContent = 'SCRIPT BY XOLOP';
script2ByLabel.style.fontFamily = '"Courier New"';
script2ByLabel.style.fontWeight = 'bold';
script2ByLabel.style.fontSize = '16px';
script2ByLabel.style.color = '#ffffff';
script2ByLabel.style.position = 'fixed';
script2ByLabel.style.top = '60px';
script2ByLabel.style.left = '50%';
script2ByLabel.style.transform = 'translateX(-50%)';
script2ByLabel.style.zIndex = '9999';
document.body.appendChild(script2ByLabel);

const scriptByLabel = document.createElement('div');
scriptByLabel.textContent = 'SCRIPT BY XOLOP';
scriptByLabel.style.fontFamily = '"Courier New"';
scriptByLabel.style.fontWeight = 'bold';
scriptByLabel.style.fontSize = '16px';
scriptByLabel.style.color = '#ffffff';
scriptByLabel.style.position = 'fixed';
scriptByLabel.style.bottom = '20px';
scriptByLabel.style.left = '50%';
scriptByLabel.style.transform = 'translateX(-50%)';
scriptByLabel.style.zIndex = '9999';
document.body.appendChild(scriptByLabel);

const script3ByLabel = document.createElement('div');
script3ByLabel.textContent = 'Telegram: @xolopdev';
script3ByLabel.style.fontFamily = '"Courier New"';
script3ByLabel.style.fontWeight = 'bold';
script3ByLabel.style.fontSize = '16px';
script3ByLabel.style.color = '#ffffff';
script3ByLabel.style.position = 'fixed';
script3ByLabel.style.bottom = '0px';
script3ByLabel.style.left = '50%';
script3ByLabel.style.transform = 'translateX(-50%)';
script3ByLabel.style.zIndex = '9999';
document.body.appendChild(script3ByLabel);

console.log(`${consoleStyles.prefix}📜 Script loaded`, consoleStyles.green);
console.log(`${consoleStyles.prefix}👨‍💻 Develop TG: [https://t.me/xolopdev]`, consoleStyles.green);
```

### Готово! Теперь вы можете использовать этот скрипт для автоматических сражений в игре PixelTap в Telegram!

<h2 align="center">Technologies & Tools</h2>

<div align="center">

![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)

</div>
