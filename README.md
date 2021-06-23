  * [BlockChain 開發人員種類](#blockchain-------)
  * [必須要擁有的技能](#--------)
  * [什麼是Dapps](#---dapps)
  * [web3](#web3)
  * [Smart Contract](#smart-contract)
  * [External Account](#external-account)
  * [Contract Account](#contract-account)
  * [Contract Definition (Solidity)](#contract-definition--solidity-)
  * [兩種類型 functions 被 called 執行的step](#-----functions---called----step)
  * [Ether & Wei](#ether---wei)
  * [Mocha](#mocha)
  * [assert](#assert)
  * [Required value from Web3 with Contracts](#required-value-from-web3-with-contracts)
  * [Solidity Type](#solidity-type)
  * [Global variable in Contract](#global-variable-in-contract)
  * [Arrays](#arrays)
  * [require() in Contract](#require---in-contract)
  * [Function Modifiers](#function-modifiers)
  * [Ethereum Architecture](#ethereum-architecture)
  * [Struct](#struct)
  * [Storage / Memory](#storage---memory)
  * [不推薦使用 array](#------array)
    + [Array / Mapping](#array---mapping)
  * [Mapping](#mapping)



## BlockChain 開發人員種類

1. 核心區塊鏈開發人員(Blockchain Developers)
    - 核心區塊鏈開發人員主要負責開發區塊鏈系統的架構，如何設計協議，共識協議的設計以及與區塊鏈技術相關的其他高級決策和開發。-而分散式軟體應用程式開發人員使用Core Blockchain開發人員設計的架構和協議來構建在區塊鏈技術上運行的分散式應用程序
    - 負責內容
        1. 區塊鏈協議的設計(Design of blockchain protocols)
        2. 設計網絡的共識協議和安全模式 (Design of consensus protocols and security patterns for the network)
        3. 網絡架構的設計 (Design of the network architecture)
        4. 監督整個網絡(Supervision of the entire network)
    - language needed: Go-long / Rust / C++ / Java
2. 分散式軟體應用程式開發人員 (Dapps developer)
    - 區塊鏈軟件開發人員有一組獨立的角色。這些角色與共識設計或系統架構無關。就像一個普通的Web開發人員如何使用核心Web架構師建立的協議和設計結構來構建Web應用程序一樣，區塊鏈軟件開發人員使用區塊鏈技術構建分散的應用程序或Dapps。他們的角色包括
    - 負責內容
        1. Dapps開發交互式前端設計 (Development of interactive front-end designs for Dapps)
        2. 與區塊鏈有關的後端開發 (Backend development pertaining to Blockchain)
        3. 監督整個運行架構的Dapps (Supervision of the entire stack running their Dapps)
        4. 開發智能合約 (Development of Smart Contracts)
    - language needed:
        1. Frontend
            - Mobile
                1. Rect-native (開發錢包)
                2. Swifi
                3. Android
            - Web
                1. React
                2. Angular
        2. Backend
            - JAVA
            - C＃
        3. Smart contract
            - Truffle
            - Solidity
            - Ember
            - Ether

## 必須要擁有的技能

1. 區塊鏈架構
    - 加密哈希函數
    - 共識
    - 分佈式分類帳技術
2. 數據結構
    - merkle樹
    - petrecia樹
        1. Blockchain使用大量數據結構和高級加密技術來構建安全且不可修改的系統
3. 加密Cryptography
    1. Blockchain是數據結構和高級密碼學的結合
4. 錢包開發
    - BIP32
    - BIP39
    - BIP44
    - multi signature
5. Web開發
    - Dapp 創建交互式圖形用戶界面
    - 基礎前端後端知識
6. 智能合約開發Smart Contract Development
    - Solidity
    - Viper
    - Chaincode
        1. 自以太坊發布以來，智能合約已成為一件大事。現在，每個區塊鏈都試圖將智能合約功能整合到其係統中, 這邊有一個點要注意的是在撰寫智能合約看似簡單但是實際上有需多需要注意與經驗的累積，例如是否智能合約能與智能合約互動還是只能允許用戶帳號與智能合約互動或是虛擬貨幣額度是否會超出上限或是否可以收負值等等的

## 什麼是Dapps

在傳統web 是通過 html/css/javascript 然後連結api 去和backend 拿資料

在Dapps世界裡 它是通過 html/css/javascript 然後 **Dapps連結的不是數據庫的API**， 而是連結 去 區塊鏈的智能合約， 然後智能合約 連結去 BlockChain

## web3

它是一個讓developer連結Ethereum network和它互動 的工具

然後 每個web3 都是return `Promise`

Life Cycle of after Send Crytocurency

1. Click submit on from
2. Address sent to backend server
3. Backend server used web3 library to create a **transaction** object
    - Transaction

[Transaction](https://www.notion.so/5f10a13241644f818d0062cc882a7085)

   4.  Backend server sent **transaction** object to the xxx test network / the network

    5.  Backend server waited for transaction to be confirmed (we need to wait, loading..) 因為 需要 去做轉換 對方的USD or EUR 而且 可能在那個server 可能是幾百億 筆交易 等等 原因:

1. 每一個 transaction 只是去一個 node 而不是 整個node 的 environment
2. 當你send transaction去到 xx(Ethereum) network 裡，不是只有你做transaction罷了 ，在同一個時間還有別人，
3. 所以 在那段時間做的交易 都在 node environment裡 做新的 block
4. 所以它需要進行數億次 無意義運算 才會需要 loading 那麼久

    6.  Backend server sent success message back to the browser.

其實 hash出來 是看 最後的result, is less than 1000 number?

為什麼叫做 Block Time， 因為 它需要去 找 哪個block 是 少過 1000的。

如果找到solution了 它還需要 update 去 別的node 所以 blockchain 的交易才會等那麼久

[Block Time](https://www.notion.so/2ec5efe671664843be8d0706bf31a383)

## Smart Contract

[Contract Account](https://www.notion.so/7b03d776a78f48af9ebc423e0dfb4ea4)

## External Account

**Metamask** 就是 External Account包括

1. Account Address
2. Public key
3. Private key

External Account 可以連結 不同的 network

## Contract Account

1. Contract Account 只能在 當天的network 他不能 和別的network access
2. Contract Account 如果 也要在 別的 network 就需要 redeploy 你的 code 去 那個 network
3. 在我們自己電腦裡的 source code Contract Source 就像JS的classes 然後 在別的network 就像Instance

## Contract Definition (Solidity)

                             Contract Definition (Solidity)

                                         |

                             Solidity Compiler

                                               |

                 |—————————————————————————————-|

Byte code ready for deployment                              Application Binary Interface (ABI)

**ABI**

JS - ABI - Bytecode，ABI是幫助 JS去 轉換去 讀 Bytecode的過度

ABI 是把block chain world transaction to JS world

[Function types](https://www.notion.so/13a7f846b5224beb9f3a38d8160cd7dc)

下面的table 很多都和 上面 Transaction table 是一樣的

[External Account to Create Contract Transaction](https://www.notion.so/f9cb786667dc40acb61d0b107bf05c25)

## 兩種類型 functions 被 called 執行的step

```jsx
pragma solidity ^0.4.17; // 用的version

contract Inbox { // 就像 JS的 class 一樣
    string public message;

    function Inbox(string initialMessage) public {
				// Inbox naming 和 contract Inbox 一樣 那是因為 這個fn 就像JS的 contructure一樣 在create instance 這個 就會 run一次罷了
        message = initialMessage;
    }

    /**
			getMessage 是 function name
      public view 是 function type
      returns (string) 是return types
    **/
    function setMessage(string newMessage) public {
        message = newMessage;
    }

    function getMessage() public view returns (string) {
        return message;
    }
}
```

[Running Contract Functions](https://www.notion.so/aeab5733412d431bb93d6cdd5ca41246)

## Ether & Wei

```jsx
1 Ether === 1,000,000,000,000,000,000 Wei

```

## Mocha

是一個 test front end / backend  / Etheruem network 的package

```jsx
let car;
beforeEach(() => {
  // run before it() callback start
  car = new Car();
})

// Car 只是一個 名字 讓我們 在 tesst的時候 知道是什麼
describe('Car', () => {
  it('can park', () => {
    assert.equal(car.park(), 'stopped')
  });

  it('can drive', () => {
    assert.equal(car.drive(), 'vroom');
  })
});
```

beforeEach 的功能 是為了為了避免在 每個 it() callback都 define instance

![web3 deploy](https://github.com/wilkersoh/note-blockchain/blob/master/images/eth-architecture.png)

argumens: ['default Value into the class constructor value']

eg: contract Inbox  裡的 function Inbox(string initialMessage)

```jsx
pragma solidity ^0.4.17; // 用的version

contract Inbox { // 就像 JS的 class 一樣
    string public message;

    function Inbox(string initialMessage) public {
				// Inbox naming 和 contract Inbox 一樣 那是因為 這個fn 就像JS的 contructure一樣 在create instance 這個 就會 run一次罷了
        message = initialMessage;
    }

    /**
			getMessage 是 function name
      public view 是 function type
      returns (string) 是return types
    **/
    function setMessage(string newMessage) public {
        message = newMessage;
    }

    function getMessage() public view returns (string) {
        return message;
    }
}
```

```jsx
pragma solidity ^0.4.17; // 用的version

contract Inbox { // 就像 JS的 class 一樣
    string public message;

    function Inbox(string initialMessage) public {
				// Inbox naming 和 contract Inbox 一樣 那是因為 這個fn 就像JS的 contructure一樣 在create instance 這個 就會 run一次罷了
        message = initialMessage;
    }

    /**
			getMessage 是 function name
      public view 是 function type
      returns (string) 是return types
    **/
    function setMessage(string newMessage) public {
        message = newMessage;
    }

    function getMessage() public view returns (string) {
        return message;
    }
}
```

```jsx
pragma solidity ^0.4.17; // 用的version

contract Inbox { // 就像 JS的 class 一樣
    string public message;

    function Inbox(string initialMessage) public {
				// Inbox naming 和 contract Inbox 一樣 那是因為 這個fn 就像JS的 contructure一樣 在create instance 這個 就會 run一次罷了
        message = initialMessage;
    }

    /**
			getMessage 是 function name
      public view 是 function type
      returns (string) 是return types
    **/
    function setMessage(string newMessage) public {
        message = newMessage;
    }

    function getMessage() public view returns (string) {
        return message;
    }
}
```

```jsx
let accounts, inbox;

beforeEach(async () => {
  // Get a list of all accounts
  accounts = await web3.eth.getAccounts()

  // Use one of those accounts to deploy
  // the contract
  inbox = await new web3.eth.Contract(JSON.parse(interface))
    .deploy({ data: bytecode, arguments: ['Hi there!'] })
    .send({ from: accounts[0], gas: '1000000' })
});

describe("Inbox", () => {
  it('deploys a contract', () => {
    console.log('inbox :>> ', inbox);
  });
});
```

## assert

1.  *use assert to check for truthiness*
2.  *use assert.ok to check for existence*

## Required value from Web3 with Contracts

![web3 contract table](https://github.com/wilkersoh/note-blockchain/blob/master/images/web3-contract-table.png)

## Solidity Type

[basic type](https://www.notion.so/1e8537afb8944382a3fc8dcb15615df1)

[Integer Ranges](https://www.notion.so/b186f91302dd466584ef6f3050111e72)

`int === int256` , `uint === uint256`, 用越大 storage需要越多

[Unsigned Integer Ranges](https://www.notion.so/c60ba9b2ee36422b8411c4f18c0f02c8)

## Global variable in Contract

[msg global variable](https://www.notion.so/5049aac9413a454d988823c673f1021b)

## Arrays

array的 不同寫法 不同用處

```jsx
contract Lottery {
  address[10]() public players; // only 10 length
	address[] public players; // dynamic length

	function pickWiiner() public {
		players = new address[](3); // [0x0000xxx, 0x0000x, 0x0000xxx]
	  players =new address[](0) // []
	}
}
```

[Reference Types](https://www.notion.so/f00a33079337471f8137bf4980f95958)

```jsx
contract Test {
	uint[] public myArray;

	function Test() public {
		myArray.push(1);
		myArray.push(10);
  }
	// return all myArray而不是 用index去call拿只有1個array的value罷了
	function getMyArray() public view returns (uint[]) {
		return myArray;
	}

	function getArrayLength() public view returns (uint) {
		return myArray.length;
	}

	function getFirstElement() public view returns (uint) {
		return myArray[0]
	}
}
```

## require() in Contract

require 會return true or false， true的話 就繼續它的code

```jsx
contract Lottery {
  function enter() public payable {
    require(msg.value > .01 ether);
		// antoher logic
  }
}
```

## Function Modifiers

Don't Repeat your self

```jsx
contract Lottery {
	function pickWinner() public {
        require(msg.sender == manager); // Repeat
				// another logic
    }

	function returnEntries() {
		 require(msg.sender == manager); // Repeat
			// another logic
	}
}
```

```jsx
function pickWinner() public restricted {
		  // another code
      uint index = random() % players.length;
      players[index].transfer(this.balance);
      players = new address[](0);
}

modifier restricted() {
	 require(msg.sender == manager);
		_; // _ (underscore)的意思是把 another logic 的 code 放過來的概念

}
```

## Ethereum Architecture

![eth architecture flow](https://github.com/wilkersoh/note-blockchain/blob/master/images/eth-architecture.png)

## Struct

例子罷了 你可以放任何你要的名字 去 符合你的 資料

我們 list 4個 name 那樣 在 create 這個 東西的時候 就需要 4 個 value

[Request Struct](https://www.notion.so/d2b45d9f012c4311b8c9e15c09d83a94)

```jsx
contract Campaign {
	struct Request {
        string description;
        uint value;
        address recipient;
        bool complete;
    }

  Request[] public requests;

  function createRequest(string description, uint value, address recipient)
        public
    {
			// 這裡要叫 memory 因為 Request({}) 是memory value來的
        Request memory newRequest = Request({
            description: description,
            value: value,
            recipient: recipient,
            complete: false
        });

				// or you can use 但是需要注意他們的順序 不然 就會放錯 value(不推薦使用這個方法， 如果上面的 Request 更改 順序 會出現error)
        Request(description, value, recipient, false);

        requests.push(newRequest);
    }
}
```

```jsx
contract Campaign {
	struct Store {
        uint productId;
        uint productValue;
    }
		// 自定義store 裡面的 value的type
		Store[] public product;
		// default 的
		address[] public approvers;
}
```

## Storage / Memory

[Data Holding Places](https://www.notion.so/677bb05754954b9cb221edb35849f98d)

例子

```jsx
contract Numbers {
  int[] public numbers;

  function Numbers() public {
    numbers.push(32);
		numbers.push(20);

		// 會error, 因為 numbers 是 point去 Storage 的int[], 但是 myArray 不是
		int[] myArray = numbers;
    // 不會error， 那是因為 你和 myArray說 point去 storage, 那樣 numbers 就會 point去 原本的 storage int[]裡, 和JS 一樣 myArray 是point像 numbers了
    int[] storage myArray = numbers;
		// use memory, 那樣 solidity 就會 把 在storage裡的 number int[] 複製一份 在 myArray 但是 是在 memory裡
		int[] memory myArray = numbers;

		makeCopy(numbers);
	  pointToSame(numbers);

  }

  function makeCopy(int[] myArray) private {
    myArray[0] = 1; // numbers[0]一樣是等於32
	}

   function makeCopy(int[] memory myArray) private {
    myArray[0] = 1; // numbers[0]一樣是等於32
	}

  function pointToSame(int[] storage myArray) private {
    myArray[0] = 1; // numbers[0]一樣是等於1
	}
}
```

## 不推薦使用 array

因為 每次 run 到 有 cost gas的 話 在 array裡 如果很大 那樣 cost 很多 gas！！！

### Array / Mapping

1. Array - Linear Time Search
    - 有1個run 1秒， 有10個 run 10秒
2. Mapping - Constant Time Search
    - 有1個run 1秒， 有10個 也run 1秒
    - `keys` are not store in mapping, 不像JS那樣
    - solidity world: 'someKeyName' → 會經過 Hashing Function → 找到 index 3 → then 它會 point去 mapping裡的 index 3
    - Values `不能`被 `loop` (not iterable)
    - 不能print全部 values出來

## Mapping

```jsx
// change to mapping;
address[] public approvers;
approvers.push(msg.sender);

mapping(address => bool) public approvers;
approvers[msg.sender] = true; // 如果沒有找到 會是 false，他沒有 undefined null 什麼的
// msg.sender are not store in the mapping as key!! just store true only;
```
