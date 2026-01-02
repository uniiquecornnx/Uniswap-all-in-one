The uniswap V2 has three main contracts 

1. Factory contract: This contract creates a Pair contract

2. Pair contracts: It holds the pair of tokens (ETH/USDC, DAI/ETH or DAI/XRP) : it allows trader to swap amongst themselves (eg in a ETH/USDC pool - trader can swap btw ETH and USDC)

2. Router contract: THis contract lets you add or remove liquidity from the pairs and also lets you swap tokens 

*the user can directly call a factory contract which will help users to deploy liquidity. but the user can also interact with the router contract - which will then call the factory contract to deply the pair of contract 