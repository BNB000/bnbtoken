<!DOCTYPE html>
<html >
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Token sale page">

    <title>Token sale</title>
   
    <script>
        var test = false; // False if contracts are on Mainnet
        var contractAddressSale = '0xeA2188B08AdCA8917FdBF9b397a8EE4abCddEAD1';
        var contractAddressToken = '0x2B046A8364AE51d7796a721AA9989Db7AcCDB857';
    </script>
    
    <style>
        
        body {font-family: Arial, "Helvetica Neue", Helvetica, sans-serif; color: #FFFFFF; background-color: #000000; font-size: 16px; font-weight: 400;}

        h1 { font-size: 24px; font-weight: 700;}
        h2 { font-size: 22px; font-weight: 500;}

        .small {
            font-size: 12px;
        }

        .err {
             color: red;
        }
        
        .green {
             color: green;
        }
        
        .blue {
             color: blue;
        }

        * {
          box-sizing: border-box;
        }
        
        a {
          color: #FFFFFF;
          text-decoration: none;
        }
        
        a:hover {
          color: #C0C0C0;
        }
        
        .clickable {
            cursor: pointer;
        }
        
        .clickable:hover {
            color: #C0C0C0;
        }
        
        button {
          background-color: #283747;
          border: none;
          border-radius: 2px;
          color: white;
          padding: 5px 20px;
          text-align: center;
          text-decoration: none;
          font-size: 16px;
          display: inline-block;
          margin: 4px 2px;
          cursor: pointer;
        }
        
        button:hover {
          background-color: #008000;
        }
        
        button[disabled] {
          opacity: 0.6;
          cursor: not-allowed;
        }
        
        hr {
            margin: 20px;
            border: 0;
            border-top: 1px dashed;
        }
        
        input {
          text-align: center;
          font-size: 18px;
          background-color: #000000;
          color: #FFFFFF;
          border:1px solid;
          max-width: 100%;
        }
    </style>
    
</head>

<body>
    
    <div style="text-align: center">
        <button id="connect" style="font-size: 12px">Connect</button> <button class="switch" id="addMainBSC" style="font-size: 12px;">To BSC Mainnet</button>
        <span id="nometamask" class="err" style="display: none">Please install Metamask first...</span>
        <div class="network small"><span id="curnet"><span class="err">Please use DApp browser/extension (e.g. <a target="_blank" href="https://metamask.io">Metamask</a>)</span></span> <span id="myAddr"></span>
        <span id="referred" style="display:none"><br>Referrer: <span id="referrer"></span></span></div>
    </div>
    
    <div style="text-align: center">
        <h1>Token info</h1>
        <h2><span id="tokenName">BNB Token</span> (<span class="tokenSymbol">BNB</span>)</h2>
        <p><a target="_blank" href="https://bscscan.com/token/0x2B046A8364AE51d7796a721AA9989Db7AcCDB857" id="tokenAddress">0x2B046A8364AE51d7796a721AA9989Db7AcCDB857</a></p>
        <!-- Reserved in case you want to show decimals and total supply: Decimals <span id="#tokenDecimals"></span> Total supply <span id="#tokenSupply"></span>-->
        <p>Do not send BNB to the token contract!</p>
        <p><button id="addToken" style="text-align: center">Add to Metamask</button> <button id="copyToken" style="text-align: center">Copy address</button></p>
    </div>
    
    <hr>
    
    <div style="text-align: center">
        <h1>Token sale status</h1>
        <h1>
            <span id="active" style="display:none" class="status green">Active</span>
