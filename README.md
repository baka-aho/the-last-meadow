# the-last-meadow


discord > ctrl+shift+i > console tab> "allow pasting" > paste this
script
```js
let weedClickCount = 0;
let grassClaimCount = 0;
let waterClickCount = 0;
let lawnmowerClickCount = 0;

// touch grass
function touchGrass() {
  const button = document.querySelector('.default__9026a[role="button"]');
  if (button) {
    button.click();
  }
}

// click weed
function clickWeed() {
  const weedButtons = document.querySelectorAll(
    '.clickable_fa03d7[role="button"]'
  );
  if (weedButtons.length > 0) {
    weedButtons[0].click();
    weedClickCount++;
  }
}

// claim grass
function claimGrass() {
  const button = document.querySelector(
    '.default__9026a.clickerButton_e9638b.enabled_e9638b.claimButton__8e695[role="button"]'
  );
  if (button) {
    button.click();
    grassClaimCount++;
  }
}

//water
function waterGrass() {
  const waterButton = document.querySelector(
    ".default__9026a.button__201d5.lookOutlined__201d5.colorWhite__201d5.sizeTiny__201d5.grow__201d5"
  );
  if (waterButton) {
    waterButton.click();
    waterClickCount++;
  }
}

//click lawnmower
function clickLawnmower() {
  const lawnmowerButton = document.querySelector(
    '.default__9026a.lawnmowerClickable__78658[role="button"]'
  );
  if (lawnmowerButton) {
    lawnmowerButton.click();
    lawnmowerClickCount++;
  }
}

function logTotals() {
  console.log(`Stats after 2 minutes:`);
  console.log(`- Total weed clicks: ${weedClickCount}`);
  console.log(`- Total grass claims: ${grassClaimCount}`);
  console.log(`- Total water clicks: ${waterClickCount}`);
  console.log(`- Total lawnmower clicks: ${lawnmowerClickCount}`);
}

// clocking
const clickInterval = setInterval(() => {
  touchGrass();
  clickWeed();
  claimGrass();
  waterGrass();
  clickLawnmower();
}, 500);

// logging
const logInterval = setInterval(logTotals, 120000);

// To stop everything later if needed:
// clearInterval(clickInterval);
// clearInterval(logInterval);
```
