How the project would look like in solidity (pseudo code):

// Variables
address public owner;
mapping (address => uint256) public balanceOf;

// Events
event Transfer(address indexed from, address indexed to, uint256 value);

// Functions
function AptosTestCoin() public {
    owner = msg.sender;
}

function transfer(address _to, uint256 _value) public {
    require(balanceOf[msg.sender] >= _value);
    require(balanceOf[_to] + _value >= balanceOf[_to]);

    balanceOf[msg.sender] -= _value;
    balanceOf[_to] += _value;

    emit Transfer(msg.sender, _to, _value);
}

function balanceOf(address _owner) public view returns (uint256) {
    return balanceOf[_owner];
}
