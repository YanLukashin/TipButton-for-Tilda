# Pay With MetaMask Buttons

[Live example](https://blockchaindev.ru/tipbutton-for-tilda)

A variety of MetaMask approved buttons for use on your own website to suggest that your users pay with MetaMask!

Usage is very easy!

1) You need to add a T123 block to your article and insert the button style code into it:

```
<style>

.tip-button {
  width: 304px;
  height: 89px;
  background-size: 100%;
  background-image: url('https://github.com/gitaaron/TipButton/raw/26d3e27544424841f53e282a5e428a76bcd001ad/images/1_pay_mm_off.png');
  cursor: pointer;
}

.tip-button:hover {
  background-image: url('https://github.com/gitaaron/TipButton/raw/26d3e27544424841f53e282a5e428a76bcd001ad/images/1_pay_mm_over.png');
}

.tip-button:active {
  background-image: url('https://github.com/gitaaron/TipButton/raw/26d3e27544424841f53e282a5e428a76bcd001ad/images/1_pay_mm_off.png');
}

</style>
```

2) After that it is worth adding, for example, block TL04 to explain to your readers what this button and where you can get an extension for the browser MetaMask.


3) Add another T123 block, where we insert the HTML of the button and the JS of our payment function:

```
<div class="tip-button"></div>
<div class="message"></div>
    
<script>

var MY_ADDRESS = '0xe493d64DC68EDae2A14fa67c6fC34E2A1566313B'

var tipButton = document.querySelector('.tip-button')

tipButton.addEventListener('click', async function() {

  if (typeof ethereum === 'undefined') {
    return renderMessage('<div>You need to install <a href=“https://metmask.io“>MetaMask </a> to use this feature.  <a href=“https://metmask.io“>https://metamask.io</a></div>')
  }

  const accounts = await ethereum.request({method:'eth_requestAccounts'})
  var user_address = accounts[0]

  try {
    const transactionHash = await ethereum.request({
      method: 'eth_sendTransaction',
      params: [
        {
          'to': MY_ADDRESS,
          'from': user_address,
          'value': '0x11c37937e08000',
        },
      ],
    })
    // Handle the result
    console.log(transactionHash)
  } catch (error) {
    console.error(error)
  }


})

function renderMessage (message) {
  var messageEl = document.querySelector('.message')
  messageEl.innerHTML = message
}

</script>
```

The image for the button is more appropriate for the style of your blog can be taken here:

## The Images

1_pay_mm_off.png
![](images/1_pay_mm_off.png)

1_pay_mm_over.png
![](images/1_pay_mm_over.png)

2_pay_mm_over.png
![](images/2_pay_mm_over.png)

2_pay_mm_off.png
![](images/2_pay_mm_off.png)

3_pay_mm_off.png
![](images/3_pay_mm_off.png)

3_pay_mm_over.png
![](images/3_pay_mm_over.png)

4_pay_mm_off.png
![](images/4_pay_mm_off.png)

4_pay_mm_over.png
![](images/4_pay_mm_over.png)

3_pay_mm_over.png
![](images/3_pay_mm_over.png)

5_pay_mm_off.png
![](images/5_pay_mm_off.png)

5_pay_mm_over.png
![](images/5_pay_mm_over.png)

6_pay_mm_off.png
![](images/6_pay_mm_off.png)

6_pay_mm_over.png
![](images/6_pay_mm_over.png)


