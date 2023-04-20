<template id="all">
<div id="all" style="text-align:center;">
  <div>
  <div style="text-align:left; font-family: 'Courier New', Courier, monospace; width: 50%; margin-left: 25%;"
      >
      <pre>
        const agenda = [{
         description:  "Commemorative fully on-chain NFT", 
         maxSupply:    "40320", //8!
         price:        "0.001 ETH", 
         image:        "fully on-chain generated .svg",
         shuffledWord: "zkSyncer",
         marksPossible: ["","!","?","a"],
        }]</pre>
  </div>
</div>
  <div id="app" v-if="!mainLoading">
    <div class="main-box">
      <div class="minter">
        <button
          class="change-button"
          :disabled="txStatus != 0"
          v-on:click="minter"
        >
          <span v-if="!txStatus">Mint your zkSyncer.Shuffled()</span>
          <span v-else-if="txStatus == 1">Waiting for confirmation...</span>
          <span v-else-if="txStatus == 2">Waiting until tx is committed...</span>
          <span v-else-if="txStatus == 3">Updating the page...</span>
        </button>
      </div>
    </div>
  </div>
  <div id="app" v-else>
    <div class="start-screen">
      <button v-on:click="connectMetamask">Connect Metamask</button>
    </div>
  </div>
  <div id="svgBox" style="text-align:center;">
    <svg xmlns="http://www.w3.org/2000/svg" width="50%" height="50%" viewBox="-8 -8 110 110" xmlns:xlink="http://www.w3.org/1999/xlink"><rect x="0" y="0" width="94" height="94" rx="10" ry="10" fill="#FFC0CB" stroke="#333377" stroke-width="1" /><text x="47" y="20" dominant-baseline="middle" text-anchor="middle" font-family="Courier New" font-size="7" fill="#333377">zkSyncer.fun</text><text x="47" y="62" dominant-baseline="middle" text-anchor="middle" font-family="Courier New" font-size="7" fill="#333377">Is your</text><text x="47" y="72" dominant-baseline="middle" text-anchor="middle" font-family="Courier New" font-size="7" fill="#333377">zkSyncer.Shuffled()</text><text x="47" y="82" dominant-baseline="middle" text-anchor="middle" font-family="Courier New" font-size="7" fill="#333377">shuffled?</text><defs><linearGradient id="myLinearGradient0" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#F0A0A0" stop-opacity="1"/><stop offset="100%" stop-color="#8C78B4" stop-opacity="1"/></linearGradient></defs><rect x="2" y="35" width="10" height="10" style="fill:url(#myLinearGradient0); " /><defs><linearGradient id="myLinearGradient1" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#8C78B4" stop-opacity="1"/><stop offset="100%" stop-color="#C82864" stop-opacity="1"/></linearGradient></defs><rect x="12" y="35" width="10" height="10" style="fill:url(#myLinearGradient1); " /><defs><linearGradient id="myLinearGradient2" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#C82864" stop-opacity="1"/><stop offset="100%" stop-color="#8A8AD8" stop-opacity="1"/></linearGradient></defs><rect x="22" y="35" width="10" height="10" style="fill:url(#myLinearGradient2); " /><text x="27" y="42" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">I</text><defs><linearGradient id="myLinearGradient3" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#8A8AD8" stop-opacity="1"/><stop offset="100%" stop-color="#A0508C" stop-opacity="1"/></linearGradient></defs><rect x="32" y="35" width="10" height="10" style="fill:url(#myLinearGradient3); " /><defs><linearGradient id="myLinearGradient4" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#A0508C" stop-opacity="1"/><stop offset="100%" stop-color="#645078" stop-opacity="1"/></linearGradient></defs><rect x="42" y="35" width="10" height="10" style="fill:url(#myLinearGradient4); " /><text x="47" y="42" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">a</text><defs><linearGradient id="myLinearGradient5" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#645078" stop-opacity="1"/><stop offset="100%" stop-color="#645078" stop-opacity="1"/></linearGradient></defs><rect x="52" y="35" width="10" height="10" style="fill:url(#myLinearGradient5); " /><text x="57" y="42" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">m</text><defs><linearGradient id="myLinearGradient6" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#645078" stop-opacity="1"/><stop offset="100%" stop-color="#F0A0A0" stop-opacity="1"/></linearGradient></defs><rect x="62" y="35" width="10" height="10" style="fill:url(#myLinearGradient6); " /><defs><linearGradient id="myLinearGradient7" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#F0A0A0" stop-opacity="1"/><stop offset="100%" stop-color="#F0A0A0" stop-opacity="1"/></linearGradient></defs><rect x="72" y="35" width="10" height="10" style="fill:url(#myLinearGradient7); " /><defs><linearGradient id="myLinearGradient8" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#F0A0A0" stop-opacity="1"/><stop offset="100%" stop-color="#F0A0A0" stop-opacity="1"/></linearGradient></defs><rect x="82" y="35" width="10" height="10" style="fill:url(#myLinearGradient8); " /><defs><linearGradient id="myLinearGradient9" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#8C78B4" stop-opacity="1"/><stop offset="100%" stop-color="#8A8AD8" stop-opacity="1"/></linearGradient></defs><rect x="2" y="45" width="10" height="10" style="fill:url(#myLinearGradient9); " /><text x="7" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">z</text><defs><linearGradient id="myLinearGradient10" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#8A8AD8" stop-opacity="1"/><stop offset="100%" stop-color="#14648C" stop-opacity="1"/></linearGradient></defs><rect x="12" y="45" width="10" height="10" style="fill:url(#myLinearGradient10); " /><text x="17" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">k</text><defs><linearGradient id="myLinearGradient11" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#14648C" stop-opacity="1"/><stop offset="100%" stop-color="#DC78A0" stop-opacity="1"/></linearGradient></defs><rect x="22" y="45" width="10" height="10" style="fill:url(#myLinearGradient11); " /><text x="27" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">c</text><defs><linearGradient id="myLinearGradient12" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#DC78A0" stop-opacity="1"/><stop offset="100%" stop-color="#14648C" stop-opacity="1"/></linearGradient></defs><rect x="32" y="45" width="10" height="10" style="fill:url(#myLinearGradient12); " /><text x="37" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">y</text><defs><linearGradient id="myLinearGradient13" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#14648C" stop-opacity="1"/><stop offset="100%" stop-color="#90A8C0" stop-opacity="1"/></linearGradient></defs><rect x="42" y="45" width="10" height="10" style="fill:url(#myLinearGradient13); " /><text x="47" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">S</text><defs><linearGradient id="myLinearGradient14" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#90A8C0" stop-opacity="1"/><stop offset="100%" stop-color="#F0A0A0" stop-opacity="1"/></linearGradient></defs><rect x="52" y="45" width="10" height="10" style="fill:url(#myLinearGradient14); " /><text x="57" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">n</text><defs><linearGradient id="myLinearGradient15" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#F0A0A0" stop-opacity="1"/><stop offset="100%" stop-color="#F0A0A0" stop-opacity="1"/></linearGradient></defs><rect x="62" y="45" width="10" height="10" style="fill:url(#myLinearGradient15); " /><text x="67" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">e</text><defs><linearGradient id="myLinearGradient16" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#F0A0A0" stop-opacity="1"/><stop offset="100%" stop-color="#90A8C0" stop-opacity="1"/></linearGradient></defs><rect x="72" y="45" width="10" height="10" style="fill:url(#myLinearGradient16); " /><text x="77" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">r</text><defs><linearGradient id="myLinearGradient17" x1="0%" y1="0%" x2="100%" y2="0%" spreadMethod="pad"><stop offset="0%" stop-color="#90A8C0" stop-opacity="1"/><stop offset="100%" stop-color="#F0A0A0" stop-opacity="1"/></linearGradient></defs><rect x="82" y="45" width="10" height="10" style="fill:url(#myLinearGradient17); " /><text x="87" y="52" font-size="9" font-family="Courier New" text-anchor="middle" fill="#333377">!</text></svg>
  </div>
</div>
</template>

<script>
import {} from "zksync-web3";
import {} from "ethers";
import { ethers } from "ethers";
import { Contract, Web3Provider, Provider } from "zksync-web3";

// eslint-disable-next-line
const ZKSYNCER_CONTRACT_ADDRESS = "0x6aBe6C42e72C34AEB2a15c12d28b48E8BD1eD91c"; // TODO: Add smart contract address
// eslint-disable-next-line
const ZKSYNCER_CONTRACT_ABI = [
    {
      "inputs": [],
      "stateMutability": "nonpayable",
      "type": "constructor"
    },
    {
      "anonymous": false,
      "inputs": [
        {
          "indexed": true,
          "internalType": "address",
          "name": "owner",
          "type": "address"
        },
        {
          "indexed": true,
          "internalType": "address",
          "name": "approved",
          "type": "address"
        },
        {
          "indexed": true,
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "Approval",
      "type": "event"
    },
    {
      "anonymous": false,
      "inputs": [
        {
          "indexed": true,
          "internalType": "address",
          "name": "owner",
          "type": "address"
        },
        {
          "indexed": true,
          "internalType": "address",
          "name": "operator",
          "type": "address"
        },
        {
          "indexed": false,
          "internalType": "bool",
          "name": "approved",
          "type": "bool"
        }
      ],
      "name": "ApprovalForAll",
      "type": "event"
    },
    {
      "anonymous": false,
      "inputs": [
        {
          "indexed": true,
          "internalType": "address",
          "name": "previousOwner",
          "type": "address"
        },
        {
          "indexed": true,
          "internalType": "address",
          "name": "newOwner",
          "type": "address"
        }
      ],
      "name": "OwnershipTransferred",
      "type": "event"
    },
    {
      "anonymous": false,
      "inputs": [
        {
          "indexed": true,
          "internalType": "address",
          "name": "from",
          "type": "address"
        },
        {
          "indexed": true,
          "internalType": "address",
          "name": "to",
          "type": "address"
        },
        {
          "indexed": true,
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "Transfer",
      "type": "event"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "to",
          "type": "address"
        },
        {
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "approve",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "owner",
          "type": "address"
        }
      ],
      "name": "balanceOf",
      "outputs": [
        {
          "internalType": "uint256",
          "name": "",
          "type": "uint256"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "getApproved",
      "outputs": [
        {
          "internalType": "address",
          "name": "",
          "type": "address"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "owner",
          "type": "address"
        },
        {
          "internalType": "address",
          "name": "operator",
          "type": "address"
        }
      ],
      "name": "isApprovedForAll",
      "outputs": [
        {
          "internalType": "bool",
          "name": "",
          "type": "bool"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [],
      "name": "mint",
      "outputs": [],
      "stateMutability": "payable",
      "type": "function"
    },
    {
      "inputs": [],
      "name": "name",
      "outputs": [
        {
          "internalType": "string",
          "name": "",
          "type": "string"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [],
      "name": "owner",
      "outputs": [
        {
          "internalType": "address",
          "name": "",
          "type": "address"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "ownerOf",
      "outputs": [
        {
          "internalType": "address",
          "name": "",
          "type": "address"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [],
      "name": "renounceOwnership",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "from",
          "type": "address"
        },
        {
          "internalType": "address",
          "name": "to",
          "type": "address"
        },
        {
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "safeTransferFrom",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "from",
          "type": "address"
        },
        {
          "internalType": "address",
          "name": "to",
          "type": "address"
        },
        {
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        },
        {
          "internalType": "bytes",
          "name": "data",
          "type": "bytes"
        }
      ],
      "name": "safeTransferFrom",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "operator",
          "type": "address"
        },
        {
          "internalType": "bool",
          "name": "approved",
          "type": "bool"
        }
      ],
      "name": "setApprovalForAll",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "bytes4",
          "name": "interfaceId",
          "type": "bytes4"
        }
      ],
      "name": "supportsInterface",
      "outputs": [
        {
          "internalType": "bool",
          "name": "",
          "type": "bool"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [],
      "name": "symbol",
      "outputs": [
        {
          "internalType": "string",
          "name": "",
          "type": "string"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "tokenURI",
      "outputs": [
        {
          "internalType": "string",
          "name": "",
          "type": "string"
        }
      ],
      "stateMutability": "view",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "from",
          "type": "address"
        },
        {
          "internalType": "address",
          "name": "to",
          "type": "address"
        },
        {
          "internalType": "uint256",
          "name": "tokenId",
          "type": "uint256"
        }
      ],
      "name": "transferFrom",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "inputs": [
        {
          "internalType": "address",
          "name": "newOwner",
          "type": "address"
        }
      ],
      "name": "transferOwnership",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "inputs": [],
      "name": "withdraw",
      "outputs": [],
      "stateMutability": "nonpayable",
      "type": "function"
    }
  ]; // TODO: Complete and import the ABI

const ETH_L1_ADDRESS = "0x0000000000000000000000000000000000000000";

export default {
  name: "App",
  data() {
    return {
      selectedToken: null,
      selectedTokenAddress: "",
      mainLoading: true,
      provider: null,
      signer: null,
      contract: null,
      canSubmit: true,
      // 0 stands for no status, i.e no tx has been sent
      // 1 stands for tx is beeing submitted to the operator
      // 2 stands for tx awaiting commit
      // 3 stands for updating the balance and greeting on the page
      txStatus: 0,

      currentBalance: "",
      currentFee: "",
    };
  },
  methods: {
    initializeProviderAndSigner() {
      // TODO: initialize provider and signer based on `window.ethereum`
      this.provider = new Provider('https://mainnet.era.zksync.io');
      // Note that we still need to get the Metamask signer
      this.signer = (new Web3Provider(window.ethereum)).getSigner();

      this.contract = new Contract(
        ZKSYNCER_CONTRACT_ADDRESS,
        ZKSYNCER_CONTRACT_ABI,
        this.signer
        );
    },
    connectMetamask() {
      window.ethereum
        .request({ method: "eth_requestAccounts" })
        .then(() => {
          if (+window.ethereum.networkVersion == 324) {
            this.loadMainScreen();
          } else {
            alert("Please switch network to zkSync Mainnet!");
          }
        })
        .catch((e) => console.log(e));
    },
    loadMainScreen() {
      this.initializeProviderAndSigner();

      if (!this.provider || !this.signer) {
        alert("Connect with Metamask!");
        return;
      }else {
      alert("Connected!");}
        this.mainLoading = false;
      
    },
    changeToken() {
      this.retreivingFee = true;
      this.retreivingBalance = true;
      const l1Token = ETH_L1_ADDRESS;
      this.provider
        .l2TokenAddress(l1Token.address)
        .then((l2Address) => {
          this.selectedToken = {
            l1Address: l1Token.address,
            l2Address: l2Address,
            decimals: l1Token.decimals,
            symbol: l1Token.symbol,
          };
          //this.updateFee();
          //this.updateBalance();
        })
        .catch((e) => console.log(e))
        .finally(() => {
         // this.retreivingFee = false;
         // this.retreivingBalance = false;
        });
    },
    async getFee() {
      // Getting the amount of gas (gas) needed for one transaction
      const feeInGas = await this.contract.estimateGas.mint();
      console.log(feeInGas);
      // Getting the gas price per one erg. For now, it is the same for all tokens.
      const gasPriceInUnits = await this.provider.getGasPrice();
      // To display the number of tokens in the human-readable format, we need to format them,
      // e.g. if feeInGas*gasPriceInUnits returns 500000000000000000 wei of ETH, we want to display 0.5 ETH the user
      return ethers.utils.formatUnits(feeInGas.mul(gasPriceInUnits), this.selectedToken.decimals);
    },

    async minter() {
        this.txStatus = 1;
      try {
          const txHandle = await this.contract.mint({
            value: ethers.utils.parseEther((0.001).toString()),
        });

          this.txStatus = 2;

          // Wait until the transaction is committed
          await txHandle.wait();
          this.txStatus = 3;
      } catch (e) {
          alert("Something went wrong!");
      }

      this.txStatus = 0;
    },
  },
}
</script>

<style>
#app {
  font-family: 'Courier New', Courier, monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:mediumslateblue;
  margin-top: 5px;
  background-color: #FFC0CB;
}

#app ul {
  display: inline-block;
}

.svgBox {
  width: 100%;
  position: relative;
  top: -15px;
  padding-top: 75px;
  margin-left: auto; 
  margin-right: auto; 
  text-align: center; 
}
.all {
  font-family: 'Courier New', Courier, monospace;
  text-align: center;
  margin-top: 0px;
  background-color: #FFC0CB;
  width: 100%;
  height: 100%;
}
.main-box {
  text-align: center;
  width: 400px;

  margin: auto;
  margin-top: 40px;
}

.change-button {
  margin-left: 0px;

}

.start-screen {
  margin-top: 5px;
  height: auto;
}

.balance {
  margin-top: 10px;
}

.refresh-button {
  margin-left: 0px;
}
</style>
