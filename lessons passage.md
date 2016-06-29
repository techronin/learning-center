# Выполнение уроков с использованием клиента сети geth.
-----------------------------------------------------

**Токен air**

<details> 
<summary>var tokenair_abi = .....;</summary>
*var tokenair_abi = [{"constant":true,"inputs":[],"name":"name","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_address","type":"address"},{"name":"_value","type":"uint256"}],"name":"approve","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"getBalance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"totalSupply","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":false,"inputs":[{"name":"_from","type":"address"},{"name":"_to","type":"address"},{"name":"_value","type":"uint256"}],"name":"transferFrom","outputs":[{"name":"","type":"bool"}],"type":"function"},{"constant":true,"inputs":[],"name":"decimals","outputs":[{"name":"","type":"uint8"}],"type":"function"},{"constant":false,"inputs":[{"name":"_value","type":"uint256"}],"name":"burn","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_value","type":"uint256"}],"name":"emission","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"balanceOf","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"symbol","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_value","type":"uint256"}],"name":"transfer","outputs":[{"name":"","type":"bool"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"address"}],"name":"allowance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[{"name":"_address","type":"address"}],"name":"getBalance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":false,"inputs":[{"name":"_address","type":"address"}],"name":"unapprove","outputs":[],"type":"function"},{"inputs":[{"name":"_name","type":"string"},{"name":"_symbol","type":"string"},{"name":"_decimals","type":"uint8"},{"name":"_start_count","type":"uint256"}],"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_value","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_spender","type":"address"},{"indexed":false,"name":"_value","type":"uint256"}],"name":"Approval","type":"event"}];*
</details>

```
var tokenair_addr = '0xb59538063903387d915486fd003a73ac0b6576d7';
var tokenair_abi = .....;
var tokenair = web3.eth.contract(tokenair_abi).at(tokenair_addr);
```

## урок 0
<details> 
<summary>var airalab_abi = .....;</summary>
*var airalab_abi = [{"constant":false,"inputs":[],"name":"ping","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"token","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_token","type":"address"}],"type":"constructor"}];*
</details>

```
var airalab_addr = '0xf89ed9fee40ac4030b48294e689391cccb89d139';
var airalab_abi = .....;
var airalab = web3.eth.contract(airalab_abi).at(airalab_addr);
airalab.ping({from:web3.eth.accounts[0], gas:200000});
```

## урок 1

1. обращаемся к BuilderDAO для создания dao

<details> 
<summary>var BuilderDAO = .....;</summary>
*var BuilderDAO = [{"constant":false,"inputs":[{"name":"_dao_name","type":"string"},{"name":"_dao_description","type":"string"},{"name":"_shares_name","type":"string"},{"name":"_shares_symbol","type":"string"},{"name":"_shares_count","type":"uint256"}],"name":"create","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_buildingCost","type":"uint256"}],"name":"setCost","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_proposal","type":"address"}],"name":"setProposal","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_cashflow","type":"address"}],"name":"setCashflow","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"buildingCost","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"getLastContract","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"getContractsOf","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_price","type":"uint256"},{"name":"_cashflow","type":"address"},{"name":"_proposal","type":"address"}],"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"instance","type":"address"}],"name":"Builded","type":"event"}];*
</details>

<details> 
<summary>var Core = .....;</summary>
*var Core = [{"constant":true,"inputs":[],"name":"name","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":true,"inputs":[{"name":"_name","type":"string"}],"name":"getModule","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[{"name":"_module","type":"address"}],"name":"getModuleName","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[],"name":"kill","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"interfaceOf","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":true,"inputs":[],"name":"founder","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_name","type":"string"}],"name":"removeModule","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"firstModule","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"description","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":true,"inputs":[{"name":"_name","type":"string"}],"name":"isConstant","outputs":[{"name":"","type":"bool"}],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_name","type":"string"},{"name":"_module","type":"address"},{"name":"_interface","type":"string"},{"name":"_constant","type":"bool"}],"name":"setModule","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"_current","type":"address"}],"name":"nextModule","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_name","type":"string"},{"name":"_description","type":"string"}],"type":"constructor"}];*
</details>

```
var b_addr = '0xf6ea06bb6319347fb9fe70ed1964ed1f5754e4de';
var BuilderDAO = .....;
var b = web3.eth.contract(BuilderDAO).at(b_addr);
b.create('My DAO', 'DAO', 'shares', 'S', 10, {from:web3.eth.accounts[0], gas:4700000})
var dao_addr = b.getLastContract()

var dao_addr = '0x2ca09b21e2adf2ce46aa241a3eeb7edf2e1c76e6';
var Core = .....;
var core = web3.eth.contract(Core).at(dao_addr);
var shares_addr = core.getModule('shares');
```

2. обращаемся к "first lesson->Execute" и передаем адрес dao в ответ получаем 100air

<details> 
<summary>var firstLesson_abi = .....;</summary>
*var firstLesson_abi = [{"constant":true,"inputs":[],"name":"ownerAir","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_dao","type":"address"},{"name":"_shares","type":"address"}],"name":"execute","outputs":[],"type":"function"},{"inputs":[{"name":"_ownerAir","type":"address"}],"type":"constructor"}];*
</details>

```
var firstLesson_addr = '0x52b422a55c13f9d4ba123065eb4e80c7727a57a0';
var firstLesson_abi = .....;
var firstLesson = web3.eth.contract(firstLesson_abi).at(firstLesson_addr);
var dao_addr = '0x2ca09b21e2adf2ce46aa241a3eeb7edf2e1c76e6';
var shares_addr = '0xb18a1a650bc431d35079e4d8d0cb0cbd773f6102';
firstLesson.execute(dao_addr, shares_addr, {from:web3.eth.accounts[0], gas:900000})
```

## урок 2

1. даем approve на 1 акцию (контракт урока ожидает approve на адрес 

<details> 
<summary>var TokenEmission = .....;</summary>
*var TokenEmission = [{"constant":true,"inputs":[],"name":"name","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_address","type":"address"},{"name":"_value","type":"uint256"}],"name":"approve","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"getBalance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"totalSupply","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":false,"inputs":[{"name":"_from","type":"address"},{"name":"_to","type":"address"},{"name":"_value","type":"uint256"}],"name":"transferFrom","outputs":[{"name":"","type":"bool"}],"type":"function"},{"constant":true,"inputs":[],"name":"decimals","outputs":[{"name":"","type":"uint8"}],"type":"function"},{"constant":false,"inputs":[{"name":"_value","type":"uint256"}],"name":"burn","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_value","type":"uint256"}],"name":"emission","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"balanceOf","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"symbol","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_value","type":"uint256"}],"name":"transfer","outputs":[{"name":"","type":"bool"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"address"}],"name":"allowance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[{"name":"_address","type":"address"}],"name":"getBalance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":false,"inputs":[{"name":"_address","type":"address"}],"name":"unapprove","outputs":[],"type":"function"},{"inputs":[{"name":"_name","type":"string"},{"name":"_symbol","type":"string"},{"name":"_decimals","type":"uint8"},{"name":"_start_count","type":"uint256"}],"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_value","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_spender","type":"address"},{"indexed":false,"name":"_value","type":"uint256"}],"name":"Approval","type":"event"}];*
</details>

```
0xc9b6815b47a14b20599ea814c2fb10260d1abdb9)
var shares_addr = '0xb18a1a650bc431d35079e4d8d0cb0cbd773f6102';
var TokenEmission = .....;
var shares = web3.eth.contract(TokenEmission).at(shares_addr);
shares.approve('0xc9b6815b47a14b20599ea814c2fb10260d1abdb9', 1, {from:web3.eth.accounts[0], gas:900000})
```

2. обращаемся к "second lesson->Execute" и передаем адрес dao в ответ получаем 100air

<details> 
<summary>var secondLesson_abi = .....;</summary>
*var secondLesson_abi = [{"constant":false,"inputs":[{"name":"_dao","type":"address"}],"name":"execute","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"ownerAir","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"airalab_learning_center","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_ownerAir","type":"address"},{"name":"_airalab_learning_center","type":"address"}],"type":"constructor"}];*
</details>

```
var secondLesson_addr = '0x34b03ffae5a6e3a3b8103d92340e009669c5ac3b';
var secondLesson_abi = .....;
var secondLesson = web3.eth.contract(secondLesson_abi).at(secondLesson_addr);
var dao_addr = '0x2ca09b21e2adf2ce46aa241a3eeb7edf2e1c76e6';
var shares_addr = '0xb18a1a650bc431d35079e4d8d0cb0cbd773f6102';
secondLesson.execute(dao_addr, shares_addr, {from:web3.eth.accounts[0], gas:900000})
```

## урок 3

1. создаем токен эзер с помощью билдера

<details> 
<summary>var BuilderTokenEther = .....;</summary>
*var BuilderTokenEther = [{"constant":false,"inputs":[{"name":"_name","type":"string"},{"name":"_symbol","type":"string"}],"name":"create","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_buildingCost","type":"uint256"}],"name":"setCost","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_proposal","type":"address"}],"name":"setProposal","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_cashflow","type":"address"}],"name":"setCashflow","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"buildingCost","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"getLastContract","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"getContractsOf","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_buildingCost","type":"uint256"},{"name":"_cashflow","type":"address"},{"name":"_proposal","type":"address"}],"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"instance","type":"address"}],"name":"Builded","type":"event"}];*
</details>

```
var b_addr = '0xa2cf52952d4d1dfd53961ce14faa976b3962b961';
var BuilderTokenEther = .....;
var b = web3.eth.contract(BuilderTokenEther).at(b_addr);
b.create('credits', 'C', {from:web3.eth.accounts[0], gas:4700000})
var credits_addr = b.getLastContract()
```

2. переводим на контракт токена 0.1
```
var credits_addr = '0x7f0e98146a268ab8e88dd48ac88dd562db226696'
eth.sendTransaction({from:web3.eth.accounts[0], to:credits_addr, value: web3.toWei('0.1', 'ether')})
```

3. запускаем выполнение урока передав адрес токена

<details> 
<summary>var thirdLesson_abi = .....;</summary>
*var thirdLesson_abi = [{"constant":false,"inputs":[{"name":"_token","type":"address"}],"name":"execute","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"ownerAir","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"airalab_learning_center","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_ownerAir","type":"address"}],"type":"constructor"}];*
</details>

```
var thirdLesson_addr = '0xd278bc0e08e8771a27846cc853d997536ee9fd65';
var thirdLesson_abi = .....;
var thirdLesson = web3.eth.contract(thirdLesson_abi).at(thirdLesson_addr);
var credits_addr = '0x7f0e98146a268ab8e88dd48ac88dd562db226696'
thirdLesson.execute(credits_addr, {from:web3.eth.accounts[0], gas:900000})
```

## урок 4

1. ipo с помощью билдера

<details> 
<summary>var BuilderIPOStart = .....;</summary>
*var BuilderIPOStart = [{"constant":false,"inputs":[{"name":"_credits","type":"address"},{"name":"_shares","type":"address"},{"name":"_start_time_sec","type":"uint256"},{"name":"_duration_sec","type":"uint256"},{"name":"_start_price","type":"uint256"},{"name":"_step","type":"uint256"},{"name":"_period_sec","type":"uint256"},{"name":"_min_value","type":"uint256"},{"name":"_end_value","type":"uint256"}],"name":"create","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_buildingCost","type":"uint256"}],"name":"setCost","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_proposal","type":"address"}],"name":"setProposal","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_cashflow","type":"address"}],"name":"setCashflow","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"buildingCost","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"getLastContract","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"getContractsOf","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_buildingCost","type":"uint256"},{"name":"_cashflow","type":"address"},{"name":"_proposal","type":"address"}],"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"instance","type":"address"}],"name":"Builded","type":"event"}];*
</details>

```
var b_addr = '0x4d2469c4e02e0ee3101e97b5b902113821c71a72';
var BuilderIPOStart = .....;
var b = web3.eth.contract(BuilderIPOStart).at(b_addr);
var credits_addr = '0x7f0e98146a268ab8e88dd48ac88dd562db226696'
var shares_addr = '0xb18a1a650bc431d35079e4d8d0cb0cbd773f6102';
var start_time = 1467096536;
var duration = 600;
var start_price = 10;
var step = 10;
var period = 60;
var min = 100;
var max = 500;
b.create(credits_addr, shares_addr, start_time, duration, start_price, step, period, min, max, {from:web3.eth.accounts[0], gas:4700000})
var ipo_addr = b.getLastContract()
```

2. переводим на контракт токена кредитов 5
```
var credits_addr = '0x7f0e98146a268ab8e88dd48ac88dd562db226696'
eth.sendTransaction({from:web3.eth.accounts[0], to:credits_addr, value: web3.toWei('5', 'ether')})
```

3. запускаем выполнение урока передав адрес токена

<details> 
<summary>var fourthLesson_abi = .....;</summary>
*var fourthLesson_abi = [{"constant":false,"inputs":[{"name":"_ipo","type":"address"}],"name":"execute","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"ownerAir","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_ownerAir","type":"address"}],"type":"constructor"}];*
</details>

```
var fourthLesson_addr = '0xf4a20b5cb8ac8d75090d901b9e94f8dba562a153';
var fourthLesson_abi = .....;
var fourthLesson = web3.eth.contract(fourthLesson_abi).at(fourthLesson_addr);
var ipo_addr = '0x7ed7d00d34641167d63072a3f9ec53b657060175'
fourthLesson.execute(ipo_addr, {from:web3.eth.accounts[0], gas:900000})
```

## урок 5

1. создаем proposal

<details> 
<summary>var CashFlow = .....;</summary>
*var CashFlow = [{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"proposals","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"shares","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_target","type":"address"},{"name":"_total","type":"uint256"},{"name":"_description","type":"string"}],"name":"proposal","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"credits","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":false,"inputs":[{"name":"_proposal","type":"address"},{"name":"_value","type":"uint256"}],"name":"refund","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_proposal","type":"address"},{"name":"_value","type":"uint256"}],"name":"fund","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_proposal","type":"address"},{"name":"_value","type":"uint256"}],"name":"fundback","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"nominalSharePrice","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"inputs":[{"name":"_credits","type":"address"},{"name":"_shares","type":"address"}],"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"proposal","type":"address"}],"name":"Created","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"proposal","type":"address"}],"name":"Updated","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"proposal","type":"address"}],"name":"Closed","type":"event"}];*
</details>

```
var cashflow_addr = '0xc6345ef22c1f6d76eabcd672081b26fb2aa78b96';
var CashFlow = .....;
var cashflow = web3.eth.contract(CashFlow).at(cashflow_addr);
cashflow.proposal(web3.eth.accounts[0], 1, "description", {from:web3.eth.accounts[0], gas:900000})
var proposal_addr = cashflow.proposals(0)
```

2. даем approve для cashflow для снятия акций

<details> 
<summary>var TokenEmission = .....;</summary>
*var TokenEmission = [{"constant":true,"inputs":[],"name":"name","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_address","type":"address"},{"name":"_value","type":"uint256"}],"name":"approve","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"getBalance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"totalSupply","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":false,"inputs":[{"name":"_from","type":"address"},{"name":"_to","type":"address"},{"name":"_value","type":"uint256"}],"name":"transferFrom","outputs":[{"name":"","type":"bool"}],"type":"function"},{"constant":true,"inputs":[],"name":"decimals","outputs":[{"name":"","type":"uint8"}],"type":"function"},{"constant":false,"inputs":[{"name":"_value","type":"uint256"}],"name":"burn","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_value","type":"uint256"}],"name":"emission","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"}],"name":"delegate","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"balanceOf","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"type":"function"},{"constant":true,"inputs":[],"name":"symbol","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_value","type":"uint256"}],"name":"transfer","outputs":[{"name":"","type":"bool"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"address"}],"name":"allowance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":true,"inputs":[{"name":"_address","type":"address"}],"name":"getBalance","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"constant":false,"inputs":[{"name":"_address","type":"address"}],"name":"unapprove","outputs":[],"type":"function"},{"inputs":[{"name":"_name","type":"string"},{"name":"_symbol","type":"string"},{"name":"_decimals","type":"uint8"},{"name":"_start_count","type":"uint256"}],"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_value","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_spender","type":"address"},{"indexed":false,"name":"_value","type":"uint256"}],"name":"Approval","type":"event"}];*
</details>

```
var shares_addr = '0xb18a1a650bc431d35079e4d8d0cb0cbd773f6102';
var TokenEmission = .....;
var shares = web3.eth.contract(TokenEmission).at(shares_addr);
var cashflow_addr = '0xc6345ef22c1f6d76eabcd672081b26fb2aa78b96';
shares.approve(cashflow_addr, 1, {from:web3.eth.accounts[0], gas:900000});
```

3. голосуем за пропосал
```
var proposal_addr = '0x0b43e23cd1ef4456d39c5c0416c486dce0ad8e03'
cashflow.fund(proposal_addr, 1, {from:web3.eth.accounts[0], gas:3000000});
```

4. запускаем выполнение урока передав адрес proposal и сумму

<details> 
<summary>var FifthLesson = .....;</summary>
*var FifthLesson = [{"constant":false,"inputs":[{"name":"_proposal","type":"address"},{"name":"_total","type":"uint256"}],"name":"execute","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"ownerAir","outputs":[{"name":"","type":"address"}],"type":"function"},{"inputs":[{"name":"_ownerAir","type":"address"}],"type":"constructor"}];*
</details>

```
var fifthLesson_addr = '0x5ec0f62b83b708a6dafc133f174ea965e99b3be5';
var FifthLesson = .....;
var fifthLesson = web3.eth.contract(FifthLesson).at(fifthLesson_addr);
var proposal_addr = '0x0b43e23cd1ef4456d39c5c0416c486dce0ad8e03'
fifthLesson.execute(proposal_addr, 1, {from:web3.eth.accounts[0], gas:900000})
```