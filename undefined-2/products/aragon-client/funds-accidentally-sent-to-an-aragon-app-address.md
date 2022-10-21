# आरागॉन ऐप के पते पर गलती से भेजे गए फंड को कैसे रिकवर करें?

यदि आपने गलती से किसी आरागॉन संगठन में इंस्टॉल किए गए ऐप के पते पर टोकन भेज दिए हैं, तो आप टोकन को पुनर्प्राप्त कर सकते हैं और उन्हें संगठन के वॉल्ट, ऑर्गनज़ैशन ऐप में भेज सकते हैं, जिसमें आपके डीएओ फंड होने चाहिए। इसे करने के दो तरीके हैं:

1. [DAO इंटरफ़ेस से इनबिल्ट (लेकिन छिपी हुई) कंसोल सुविधा का उपयोग करना](https://app.gitbook.com/o/3h8kxj8geKVXgyMnGbYT/s/qbJnwSlPYXvqQ6buM1wp/)
2. [कमांड लाइन से आरागॉनसीएलआई का उपयोग करना](https://app.gitbook.com/o/3h8kxj8geKVXgyMnGbYT/s/qbJnwSlPYXvqQ6buM1wp/)



{% hint style="danger" %}
हम कंसोल विकल्प का उपयोग करने की दृढ़ता से अनुशंसा करते हैं क्योंकि यह बहुत आसान है
{% endhint %}



### कंसोल सुविधा का उपयोग करके अपने धन की वसूली करें

Use the following steps:

अपना डीएओ खोलें, और अपने डीएओ वेब पते के अंत में /कंसोल(/console) जोड़ें। यूआरएल इस तरह दिखेगा: `https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
उपरोक्त(रीप्लैस)  URL में को अपने DAO के नाम से बदलें `<your-dao-name>`&#x20;
{% endhint %}



आपको नीचे जैसा कुछ देखना चाहिए:

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>



अगला Exec चुनें जो DAO में लेनदेन करने के लिए उपयोग किया जाने वाला एक कमांड है।

यहां आप उस ऐप का चयन करें जिस पर गलती से फंड भेजा गया था। इस उदाहरण में, धनराशि गलती से फाइनैन्स ऐप को भेज दी गई थी, इसलिए हम फाइनैन्स(`Finance)` का चयन करते हैं:

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>



[जीथब](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/finance/contracts/Finance.sol#L399-L410) पर फाइनेंस ऐप के सोर्स कोड में आप एक फंक्शन पा सकते हैं जिसे रिकवर टूवॉल्ट कहा जाता है(`recoverToVault)`, ठीक वही जो हमें चाहिए!

अब हम इस फंक्शन को आरागॉन कंसोल से कॉल करेंगे। ऐसा करने के लिए हमें कंसोल में कमांड में रिकवरीटॉवॉल्ट (पता \_token) (`recoverToVault(address _token))`जोड़ना होगा, लेकिन पहले हम पता \_token(`address _token)` को टोकन के अनुबंध पते से बदल देंगे जो गलती से फाइनेंस ऐप को भेज दिया गया था।

इस उदाहरण के मामले में पता 0x3255D2D022Ef80F58dA2D107235010367cCdF0fD है, इसलिए हम कंसोल में कमांड में `recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)` जोड़ देंगे। इस उदाहरण के लिए पूर्ण आदेश अब निम्नलिखित है:

```
exec/0xa4bb9c789cccdce9565ee5a6d066dccef05c6a42/recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)
```



अब एंटर पर क्लिक करें:

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>



अब **लेन-देन बनाएँ** पर क्लिक करके लेन-देन की पुष्टि करें:

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>



फिर अपने वेब3 वॉलेट (अक्सर मेटामास्क) में लेनदेन की पुष्टि करें।

{% hint style="danger" %}
सुनिश्चित करें कि आप एक वेब3 खाते का उपयोग करते हैं जिसने या तो डीएओ बनाया है या (और) इस लेनदेन पर हस्ताक्षर करने के लिए आपके डीएओ-टोकन धारण कर रहा है
{% endhint %}

अब अपने संगठन में वित्त ऐप पर जाएं, और आपके फंड जादुई रूप से वहां दिखाई देने चाहिए!

इस उदाहरण में वित्त से Vault ऐप में BRT टोकन बरामद किए गए हैं:



****

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

###

### aragonCLI का उपयोग करके अपने धन की वसूली करें(रिकवर)

निम्नलिखित चरणों का प्रयोग करें:

1. [आरागॉनसीएलआई ](https://hack.aragon.org/developers/tools/aragoncli)स्थापित करें जो आरागॉन संगठनों के साथ बातचीत करने के लिए एक कमांड लाइन इंटरफेस है।
2. आरागॉन संगठनों के लिए डेटा (जैसे एबीआई) तक पहुंचने के तरीके के साथ आरागॉनसीएलआई प्रदान करने के लिए अपने टर्मिनल में आरागॉन आईपीएफ(`aragon ipfs)` चलाएं।
3. [AragonCLI के उपयोग के लिए एक निजी कुंजी सेट करें,](https://hack.aragon.org/developers/tools/guides/how-to-sign-with-web3-providers) फिर गैस के भुगतान के लिए इस निजी कुंजी के पते पर कुछ ईथर भेजें।
4. आरागॉनसीएलआई से निम्नलिखित ट्रांजैक्शन कमांड भेजें, प्रत्येक "एड्रेस" को आपके अटके हुए ट्रांजेक्शन से संबंधित संबंधित पते से बदलें:



```powershell
dao exec OrganizationAddress AppAddress recoverToVault TokenContractAddress --environment aragon:mainnet
```



जहां `OrganizationAddress` अटके हुए धन को रखने वाले संगठन का पता है, `AppAddress` उस ऐप का पता है जिसे आपने अटकी हुई धनराशि भेजी थी, और `TokenContractAddress` आपके द्वारा भेजे गए टोकन के लिए टोकन अनुबंध का पता है।

उदाहरण के लिए, यदि आपने [दाई](https://etherscan.io/token/0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359) को <mark style="color:blue;">genesis.aragonid.eth</mark> संगठन के वित्त ऐप पते पर भेजा है, तो आप aragonCLI से जो लेनदेन आदेश भेजेंगे, वह होगा:

```
dao exec 0x8A83D4bCE45b4C4F751f76cf565953D1E4A3BF0a 0x98516C82Bda8B3dE6E2670B718848949Ae6a4643 recoverToVault 0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359 --environment aragon:mainnet
```

[इस](https://github.com/ethereum-cat-herders/funding/issues/2#issuecomment-477174751) GitHub टिप्पणी में इन चरणों का दस्तावेजीकरण करने के लिए क्रिस हॉबक्रॉफ्ट को धन्यवाद।
