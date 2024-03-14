
https://gist.github.com/shayanb/cd495e23c7cf1a8b269f8ce7fd198538

トークン | 機能 | 既知の脆弱性 | リソース | 例
--- | --- | --- | --- | ---
ERC20 | Allowance | 二重引き出し（フロントランニング） | ERC20トークンの複数引き出し攻撃の解決 |
 | decimals() | decimalsが18より多い可能性がある | | YamV2は24のdecimalsを持つ
 | 複数引き出し攻撃を防ごうとするトークンを考慮しない | Perpetual Protocol Audit issue 3.12 |
 | Unprotected transferFrom() | Bancor Network Hack 2020 - 1inch |
 | 外部呼び出し | チェックされていないCall返却値 | チェックされていないcall返却値 |
 | 予期せぬrevertでのDoS | 予期せぬrevertでのDoS |
 | Transfers | Falseを返す代わりにRevertする可能性がある |
 | 戻り値の欠如 | 戻り値がないバグ - 少なくとも130のトークンが影響 |
 | BalanceOf() | 内部会計の不一致と実際のバランス | aToken引き出しの脆弱性 | aToken |
 | Blacklistable | ブラックリストに登録されたアドレスはトークンの送受信ができない | CENTREがUSDCを持つアドレスを初めてブラックリストに登録 | USDC (FiatToken) |
 | Mintable / Burnable | 信頼できるアクターによってTotalSupplyが変更される |
 | Pausable | すべての機能を信頼できるアクターによって一時停止できる |
 | Deflationary Tokens | 転送から手数料を取る | 内部会計の不一致と実際のバランス | 非標準のERC20デフレトークンのインシデント | STA, STONK |
 | Inflationary Tokens | トークン所有者にAirDrop利息を与える | 内部会計の不一致と実際のバランス | | Compound |
ERC1400 | Permissioned Addresses | 特定のアドレスから/への転送をブロックできる | | Polymath tokens |
 | Forced Transfers | 信頼できるアクターが資金を好きなように転送する能力を持つ |
ERC777 | Callbacks / Hooks | 再入力 | Uniswap audit, OpenZeppelin Example Uniswap exploit, imBTC Uniswap exploit | pTokens |
 | 受信者がGasTokenをマイニング |
 | 受信者が転送をブロック | 反復的なプッシュ転送の場合、すべての転送をブロックする可能性がある |
ERC1644 | Forced Transfers | コントローラーが資金を盗む能力を持つ |
ERC621 | TotalSupplyの制御 | TotalSupplyを信頼できるアクターによって変更できる |
ERC884 | キャンセルと再発行 | トークン実装者はアドレスをキャンセルし、そのトークンを新しいアドレスに移動する能力を持つ |
 | Whitelisting | トークンはホワイトリストに登録されたアドレスにのみ送信できる |
