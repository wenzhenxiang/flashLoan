# flashLoan
闪电贷

学习第一笔闪电贷参考
https://github.com/wenzhenxiang/flashLoan/blob/main/hecoFirstFlash.sol


目前已支持heco链借贷三傻与xcom借贷平台的清算功能(只支持以下币种的借贷清算，hbtc,eth,husd,usdt,mdx,ht,hltc,hfil)

Xcom闪电贷清算合约地址：
0xAD7958B141fd151910A67e973A4e1173d38C5801
Xcom闪电贷清算合约abi文件：
FlashLiquidationAdapter.json


借贷三傻闪电贷清算合约地址：
0x6524a87301129E3419ad8E1eC8d6A5Ef133d59B2
借贷三傻闪电贷清算合约abi文件：
CompflashLiquidationAdapter.json


清算方法：
通过abi及合约地址获取合约实例，例如flashLiquidationAdapter
然后执行Execute函数，参数为
  struct LiquidationParams {
    address collateralCtoken;   // 清算抵押币的ctoken地址
    address borrowedCtoken;     // 清算贷款币的ctoken地址
    address user;               // 清算用户地址
    uint256 debtToCover;        // 清算额度
    bool useEthPath;            // mdex交易是否添加ht路径
  }
参考如下
flashLiquidationAdapter.Execute(["0xB16Df14C53C4bcfF220F4314ebCe70183dD804c0","0x4937A83Dc1Fa982e435aeB0dB33C90937d54E424","0x42278EB6A4Ba1F79077a0F048E6d5f7713B8E6cc",'1000000000000', false]);


