<template>
<button @click="connect">
    <div v-if="address.length == 0">
        <img :src="image" alt=""> Connect Wallet
    </div>
    <div v-else>
        <p>{{address}}</p>
    </div>
</button>
</template>

<script>
export default{
    name: "ConnectButton",
    data(){
        return{
            image: "https://cdn.iconscout.com/icon/free/png-256/metamask-2728406-2261817.png",
            address: ""
        }
    },
    methods: {
       async connect(){
             let {ethereum} = window;
             let accounts =  await ethereum.request({method: "eth_requestAccounts"})
             let acc = accounts[0]
             this.address = `${acc.substring(6,'')}...${acc.substring(38,43)}`
        }
    },
}
</script>

<style extends>
button{
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 15px;
    background-color: white;
    border: 1px solid #000;
    border-radius: 20px;
    padding: 10px;
    cursor: pointer;
}
button:hover{
    background-color: #000;
    color: white;
    border: 1px solid white;
}
img{
    width: 20px;
    margin-right: 10px;
}
    
</style>