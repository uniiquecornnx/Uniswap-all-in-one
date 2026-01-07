Function from UniswapV2Router02.sol


1. swapExactTokensForTokens(uint amountIn, uint amountOutMin, address[] calldata path, uint deadline) : This function will swap all the input for max output, for eg if you have 1000 DAI and you want to swap it for max WETH

//How it works: it is gonna call a UniswapV2Library.getAmountsOut and return  an array of uint

//Tokens are directly transferred to the Pair contract instead of Pair contract calling a transferFrom - this step is automated by swapExactTokensForTokens where inside it has a _swap function that runs on the Pair contract

*Note: _swap(uint[] memory amounts, address[] memory path, address _to)


2. getAmountsOut(address factory, uint amountIn, address[] memory path) internal view return(uint)

//What it does: Calculate the amounts-out for each swap and return the result as an array of uint

//Internal functions: 
getReserves() = interanl balance of token inside the Pair contract 
getAmountOut() = use the previous output for a particular input

> uint amountInWithFee = amountIn.mul(997);
> uint numerator = amountInWithFee.mul(reserveOut);
> uint denominator = reserveIn.mul(1000).add(amountInWithFee);
> amountOut = numerator/denominator;

3. swapTokensForExactTokens(uint amountOut, uint amountInMax, address[] calldata path, address to, uint daedline)  : user wants a minimium input for some specified output

Functions from UniswapV2Library.sol

1. getAmountsOut & getAmountsIn

3. getAmountOut()