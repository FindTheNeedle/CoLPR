# CoLPR

**System-Wide Ransomware Attack Detection via Perturbation-Resilient Representation Learning**  
(*Paper under peer review*)

---

## 📄 About This Repository

This repository accompanies our paper, currently under peer review:

> **System-Wide Ransomware Attack Detection via Perturbation-Resilient Representation Learning**  
> *[Authors omitted for anonymity during review]*

### 📝 Summary of Contributions

Ransomware has evolved into stealthy, system-level attacks that disguise malicious activity among benign applications, rendering process-level detection ineffective.  
We present **CoLPR**, a contrastive self-supervised learning framework for **perturbation-resilient, system-wide ransomware detection**.

Key contributions:
1. **Perturbation-Resilient Representation Learning** – We propose a novel data augmentation strategy that produces strongly perturbed yet realistic behavioral data for training, enabling resilience against interference from other running applications.
2. **Environment-Aware Fine-Tuning** – The learned encoder is adapted to specific deployment environments, achieving accurate detection even under multi-application interference.
3. **Timely Detection** – Across three real-world deployment environments, CoLPR achieved:
   - **100% Recall**
   - **4.58s average detection delay** (well within the 60-second short-term backup window)
   - **98.8% overall Accuracy**
4. **Robustness to Unseen Families** – Successfully detected attacks from 12 previously unseen ransomware families under strong perturbations.

---

## 📂 Purpose of This Repository

This repository releases **supplementary materials** for our paper, specifically:

- **Ransomware executable pool composition**:
  - Ransomware family names
  - SHA-256 hashes
  - MalwareBazaar Database links

The goal is to help the research community **replicate or extend** our work by providing full transparency on the ransomware families we tested.

---

## 🦠 Ransomware Categories

Our ransomware pool covers **96 families** in total, divided into:

- **84 user-privileged families** – Can execute without administrator rights.
- **12 super-privileged families (UNSEEN)** – Require administrator privileges to execute.

### 1️⃣ User-Privileged Families

These ransomware families execute at the **user privilege level** and can encrypt files without elevated permissions. They are safe to evaluate in automated environments, making them suitable for large-scale behavioral dataset generation.  

---

### 2️⃣ Super-Privileged Families (UNSEEN)

Some ransomware families require **administrator privileges** and can inflict severe system damage, including:

- Disabling **Windows Recovery Environment (Windows RE)**
- Destroying hidden disk images

To maintain **full automation**, we mark these as **UNSEEN** and collect their behavioral samples **manually** by restoring the system after each run. This allows us to test CoLPR’s **generalizability** to novel, high-impact threats.

---

## 📊 Ransomware Executable Pool Composition

| Family Name | Privilege Level | SHA-256 | MalwareBazaar Link |
|-------------|----------------|---------|--------------------|
| Abyss | User | `9243bdcbe30fbd430a841a623e9e1bcc894e4fdc136d46e702a94dad4b10dfdc` | [Link](https://bazaar.abuse.ch/sample/9243bdcbe30fbd430a841a623e9e1bcc894e4fdc136d46e702a94dad4b10dfdc/) |
| AgentTesla | User | '2b459daf113570ef0b9772a9f262a571f034e29a1bc35072b00b38024a863132' | [Link](https://bazaar.abuse.ch/sample/2b459daf113570ef0b9772a9f262a571f034e29a1bc35072b00b38024a863132/) |
| Ako | User | 'a5eb835060919717bdddb6d66b08618586d55bfb41ccef791c4b5beb7ee319a3' | [Link](https://bazaar.abuse.ch/sample/a5eb835060919717bdddb6d66b08618586d55bfb41ccef791c4b5beb7ee319a3/) |
| Avoslocker | User | 'bff12a83b1fc2e0ad0000ad9b68abc8eada559bb1094caaf5b9f52887df23705' | [Link](https://bazaar.abuse.ch/sample/bff12a83b1fc2e0ad0000ad9b68abc8eada559bb1094caaf5b9f52887df23705/) |
| Bagli | User | '68eddce0bad4515b40581f454e479a42fdd3b89e004fbba162acf339fbe46f09' | [Link](https://bazaar.abuse.ch/sample/68eddce0bad4515b40581f454e479a42fdd3b89e004fbba162acf339fbe46f09/) |
| Bentley | User | 'a4d9cf67d111b79da9cb4b366400fc3ba1d5f41f71d48ca9c8bb101cb4596327' | [Link](https://bazaar.abuse.ch/sample/a4d9cf67d111b79da9cb4b366400fc3ba1d5f41f71d48ca9c8bb101cb4596327/) |
| Blackbasta | User | '2413841b2f5f656e269f61644d3957847b199107bb6b141c3208a03df59f0759' | [Link](https://bazaar.abuse.ch/sample/2413841b2f5f656e269f61644d3957847b199107bb6b141c3208a03df59f0759/) |
| Blackkingdom | User | '63d6c419a8229bc7fc2089a2899d27bac746de0e96368e2a49d7c7754abd29f4' | [Link](https://bazaar.abuse.ch/sample/63d6c419a8229bc7fc2089a2899d27bac746de0e96368e2a49d7c7754abd29f4/) |
| Blackmatter | User | '374f9df39b92ccccae8a9b747e606aebe0ddaf117f8f6450052efb5160c99368' | [Link](https://bazaar.abuse.ch/sample/374f9df39b92ccccae8a9b747e606aebe0ddaf117f8f6450052efb5160c99368/) |
| Blacksnake | User | 'e4c2e0af462ebf12b716b52c681648d465f6245ec0ac12d92d909ca59662477b' | [Link](https://bazaar.abuse.ch/sample/e4c2e0af462ebf12b716b52c681648d465f6245ec0ac12d92d909ca59662477b/) |
| Conti | User | 'a83796aa471d9710b44d2ca9196d990b189cb9cbe1846e688be8660c5a6298dd' | [Link](https://bazaar.abuse.ch/sample/a83796aa471d9710b44d2ca9196d990b189cb9cbe1846e688be8660c5a6298dd/) |
| Coom | User | 'baba76d578be903c9d78e3d6417636ba6a8069cafe9ccccdfce2bc19b43fc299' | [Link](https://bazaar.abuse.ch/sample/baba76d578be903c9d78e3d6417636ba6a8069cafe9ccccdfce2bc19b43fc299/) |
| Crylock | User | 'b1ac46470933de2096f95f35116dc3dd2a52b416150b75dc3d5e3ee4d521a09a' | [Link](https://bazaar.abuse.ch/sample/b1ac46470933de2096f95f35116dc3dd2a52b416150b75dc3d5e3ee4d521a09a/) |
| Cryptfile2 | User | 'ac50a0eeec0bddc53420d110cf8161fd17c53a4136992132b2fa5b0c09a84cce' | [Link](https://bazaar.abuse.ch/sample/ac50a0eeec0bddc53420d110cf8161fd17c53a4136992132b2fa5b0c09a84cce/) |
| Cylan | User | '03097f75904007de33f69ec77e02146fe2a0b3d3b2a923640677bb1f46815b07' | [Link](https://bazaar.abuse.ch/sample/03097f75904007de33f69ec77e02146fe2a0b3d3b2a923640677bb1f46815b07/) |
| Cylance | User | '7a5e813ec451cde49346d7e18aca31065846cafe52d88d08918a297196a6a49f' | [Link](https://bazaar.abuse.ch/sample/7a5e813ec451cde49346d7e18aca31065846cafe52d88d08918a297196a6a49f/) |
| Dalexis | User | '3729c1d683690f752732ec18372a555abfb0d20c02ea3f9fe60ca6577722c9a8' | [Link](https://bazaar.abuse.ch/sample/3729c1d683690f752732ec18372a555abfb0d20c02ea3f9fe60ca6577722c9a8/) |
| Darkbit | User | '9107be160f7b639d68fe3670de58ed254d81de6aec9a41ad58d91aa814a247ff' | [Link](https://bazaar.abuse.ch/sample/9107be160f7b639d68fe3670de58ed254d81de6aec9a41ad58d91aa814a247ff/) |
| Darkside | User | '315d043b99f988ce9d9f69d7225292eb44623a97c1a029933b62ede699fa9f13' | [Link](https://bazaar.abuse.ch/sample/315d043b99f988ce9d9f69d7225292eb44623a97c1a029933b62ede699fa9f13/) |
| DECAF | User | 'a471fdf6b137a6035b2a2746703cd696089940698fd533860d34e71cc6586850' | [Link](https://bazaar.abuse.ch/sample/a471fdf6b137a6035b2a2746703cd696089940698fd533860d34e71cc6586850/) |
| Dharma | User | '2210baa7b596879b413965c17f9f33dbf698ac183b2b82329d397c73dee5fc3d' | [Link](https://bazaar.abuse.ch/sample/2210baa7b596879b413965c17f9f33dbf698ac183b2b82329d397c73dee5fc3d/) |
| Diavol | User | 'b3da793a00eebaf8987fe2b759369e3d7ff02d91111c219c707bcb9709357637' | [Link](https://bazaar.abuse.ch/sample/b3da793a00eebaf8987fe2b759369e3d7ff02d91111c219c707bcb9709357637/) |
| Donex | User | '0adde4246aaa9fb3964d1d6cf3c29b1b13074015b250eb8e5591339f92e1e3ca' | [Link](https://bazaar.abuse.ch/sample/0adde4246aaa9fb3964d1d6cf3c29b1b13074015b250eb8e5591339f92e1e3ca/) |
| DragonForce | User | '1ccf8baf11427fae273ffed587b41c857fa2d8f3d3c6c0ddaa1fe4835f665eba' | [Link](https://bazaar.abuse.ch/sample/1ccf8baf11427fae273ffed587b41c857fa2d8f3d3c6c0ddaa1fe4835f665eba/) |
| Elbie | User | '60c24a4c6b54b1f4baeaee585e5e2486bbd3ab4733de36bb28da1fdb20596e21' | [Link](https://bazaar.abuse.ch/sample/60c24a4c6b54b1f4baeaee585e5e2486bbd3ab4733de36bb28da1fdb20596e21/) |
| Eternitystealer | User | 'f33c1422f778eb04ab20ee3033a88789c0063031b75a2742c54133078341753f' | [Link](https://bazaar.abuse.ch/sample/f33c1422f778eb04ab20ee3033a88789c0063031b75a2742c54133078341753f/) |
| Expiro | User | '877e8f233f5b9b5eebd23144aae4b6597f9c8a8df598182abe1ec2c300025e28' | [Link](https://bazaar.abuse.ch/sample/877e8f233f5b9b5eebd23144aae4b6597f9c8a8df598182abe1ec2c300025e28/) |
| Fog | User | 'f8bdd832ce22b529f0eae14e642bb95e990e317707b094a225670a15d5c8ca1f' | [Link](https://bazaar.abuse.ch/sample/f8bdd832ce22b529f0eae14e642bb95e990e317707b094a225670a15d5c8ca1f/) |
| Gandcrab | User | '0400e0f6d0075051aa9e2e1186fe0d79739e8441827a9942148b5a24931e3f2c' | [Link](https://bazaar.abuse.ch/sample/0400e0f6d0075051aa9e2e1186fe0d79739e8441827a9942148b5a24931e3f2c/) |
| Globelmposter | User | 'd9135507e8dbcf15a852ec34623ea6b6d633e10032c94f187ef357ba821af893' | [Link](https://bazaar.abuse.ch/sample/d9135507e8dbcf15a852ec34623ea6b6d633e10032c94f187ef357ba821af893/) |
| Glupteba | User | '13d7401a23c41df79a1c50d730f3d26816796376b64525613c30995b7b14c7b4' | [Link](https://bazaar.abuse.ch/sample/13d7401a23c41df79a1c50d730f3d26816796376b64525613c30995b7b14c7b4/) |
| GPcode | User | 'e9ffda70e3ab71ee9d165abec8f2c7c52a139b71666f209d2eaf0c704569d3b1' | [Link](https://bazaar.abuse.ch/sample/e9ffda70e3ab71ee9d165abec8f2c7c52a139b71666f209d2eaf0c704569d3b1/) |
| Hakunamatata | User | 'a60af750115389bf7891c982f42cb30f7436e996072d6bd1f04930c67cb4649e' | [Link](https://bazaar.abuse.ch/sample/a60af750115389bf7891c982f42cb30f7436e996072d6bd1f04930c67cb4649e/) |
| Heda | User | '0a5ba8d248080666c7ea5bd9c325452fad055a00e194989a34bd816c26a62328' | [Link](https://bazaar.abuse.ch/sample/0a5ba8d248080666c7ea5bd9c325452fad055a00e194989a34bd816c26a62328/) |
| HellCat | User | 'b8e71845cc8ccd668a3436d1952a6c57649974bb8399e599dc33afc4c0843be7' | [Link](https://bazaar.abuse.ch/sample/b8e71845cc8ccd668a3436d1952a6c57649974bb8399e599dc33afc4c0843be7/) |
| Helldown | User | '0b090f1471629e7e852850166eb814c09ace3c88f0c9f5e5ffeb1b9f754875aa' | [Link](https://bazaar.abuse.ch/sample/0b090f1471629e7e852850166eb814c09ace3c88f0c9f5e5ffeb1b9f754875aa/) |
| Helloxd | User | '435781ab608ff908123d9f4758132fa45d459956755d27027a52b8c9e61f9589' | [Link](https://bazaar.abuse.ch/sample/435781ab608ff908123d9f4758132fa45d459956755d27027a52b8c9e61f9589/) |
| Imps | User | 'e8f164916c026d7892113a2b479d3b494f7bfc29285cf1f04c9ff670d30f7abb' | [Link](https://bazaar.abuse.ch/sample/e8f164916c026d7892113a2b479d3b494f7bfc29285cf1f04c9ff670d30f7abb/) |
| INC | User | '0315dbb793f855f154aa8d227151f1098bd9b580a4f85064648b85bac1321663' | [Link](https://bazaar.abuse.ch/sample/0315dbb793f855f154aa8d227151f1098bd9b580a4f85064648b85bac1321663/) |
| Infinitylock | User | '27a1f89ce5a37815010c8411dddec85d5d66e81a957ad722fbd2dc64f99651c8' | [Link](https://bazaar.abuse.ch/sample/27a1f89ce5a37815010c8411dddec85d5d66e81a957ad722fbd2dc64f99651c8/) |
| Intercobros | User | 'ade5780b02f010a91f0684089100035366af865caba9c6beb66a271ccc89f2ae' | [Link](https://bazaar.abuse.ch/sample/ade5780b02f010a91f0684089100035366af865caba9c6beb66a271ccc89f2ae/) |
| Kadavaro | User | 'b7ca2dde7789da13d1b8729cc2ef3d5dc596cbd710a06c17ff6eb4ef2d9d1182' | [Link](https://bazaar.abuse.ch/sample/b7ca2dde7789da13d1b8729cc2ef3d5dc596cbd710a06c17ff6eb4ef2d9d1182/) |
| Karma | User | '34629751d8202be456dcf149b516afefc980a9128dd6096fd6286fee530a0d20' | [Link](https://bazaar.abuse.ch/sample/34629751d8202be456dcf149b516afefc980a9128dd6096fd6286fee530a0d20/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Kuiper | User | '0162641163a30a2edff787eeecc733ab1de46f03e213743dc768d39eb3075985' | [Link](https://bazaar.abuse.ch/sample/0162641163a30a2edff787eeecc733ab1de46f03e213743dc768d39eb3075985/) |
| Lockbit | User | '25fba0e92d00184dde662c7d30aff006851dba296daa6f6f82ce797b66789ed2' | [Link](https://bazaar.abuse.ch/sample/25fba0e92d00184dde662c7d30aff006851dba296daa6f6f82ce797b66789ed2/) |
| Lockdown | User | '6b2eef51eb8d2da78055f70b99a85766ba6731a99a5c1b90eaaa80a47ca42702' | [Link](https://bazaar.abuse.ch/sample/6b2eef51eb8d2da78055f70b99a85766ba6731a99a5c1b90eaaa80a47ca42702/) |
| Locky | User | 'dafec2b2af3ace2c478382f9366f6cbc9b9579f2c9a4273150fc33a2ccd59284c' | [Link](https://bazaar.abuse.ch/sample/afec2b2af3ace2c478382f9366f6cbc9b9579f2c9a4273150fc33a2ccd59284c/) |
| Luka | User | '30390db8ef77afdb6add86f7f2990a142823401078ab237020933d0423374b27' | [Link](https://bazaar.abuse.ch/sample/30390db8ef77afdb6add86f7f2990a142823401078ab237020933d0423374b27/) |
| Lynx | User | 'b378b7ef0f906358eec595777a50f9bb5cc7bb6635e0f031d65b818a26bdc4ee' | [Link](https://bazaar.abuse.ch/sample/b378b7ef0f906358eec595777a50f9bb5cc7bb6635e0f031d65b818a26bdc4ee/) |
| Makop | User | 'aaf7bb9ad358726ca367f1827686dc15fea925f26ab1e201a2768c67472e8890' | [Link](https://bazaar.abuse.ch/sample/aaf7bb9ad358726ca367f1827686dc15fea925f26ab1e201a2768c67472e8890/) |
| Mallox | User | '06699c98ed2ef759b2434ac5777a2886b966c0ffa1c96c046f5cde77fe833784' | [Link](https://bazaar.abuse.ch/sample/06699c98ed2ef759b2434ac5777a2886b966c0ffa1c96c046f5cde77fe833784   /) |
| Mammon | User | 'f5ed57e822e8d236cda4e4547f2d9af2caa9fb37e90406ee6dd253d014fcd8a9' | [Link](https://bazaar.abuse.ch/sample/f5ed57e822e8d236cda4e4547f2d9af2caa9fb37e90406ee6dd253d014fcd8a9/) |
| Mespinoza | User | 'af99b482eb0b3ff976fa719bf0079da15f62a6c203911655ed93e52ae05c4ac8' | [Link](https://bazaar.abuse.ch/sample/af99b482eb0b3ff976fa719bf0079da15f62a6c203911655ed93e52ae05c4ac8/) |
| Mimic | User | '2423f6e4b6f015042c4de4a4ad457629b7c4737ec19352abac9dd6136ba46d68' | [Link](https://bazaar.abuse.ch/sample/2423f6e4b6f015042c4de4a4ad457629b7c4737ec19352abac9dd6136ba46d68/) |
| Moneymessage | User | '8be41efd6e6ace53b8c59344be2ba91fe41003987a8e38484b20760d7c400a42' | [Link](https://bazaar.abuse.ch/sample/8be41efd6e6ace53b8c59344be2ba91fe41003987a8e38484b20760d7c400a42/) |
| Mountlocker | User | '8b539f3ba05fe82c4f992ffbeb6ab55151b36dce2d03b64721e966dedf82be81' | [Link](https://bazaar.abuse.ch/sample/8b539f3ba05fe82c4f992ffbeb6ab55151b36dce2d03b64721e966dedf82be81/) |
| Nefilim | User | '45e35c9b095871fbc9b85afff4e79dd36b7812b96a302e1ccc65ce7668667fe6' | [Link](https://bazaar.abuse.ch/sample/45e35c9b095871fbc9b85afff4e79dd36b7812b96a302e1ccc65ce7668667fe6/) |
| Nemty | User | '2d4b2b807ace9dfc3f13962c65f1b6b9b6ba80394c517729ada50d6302792d9c' | [Link](https://bazaar.abuse.ch/sample/2d4b2b807ace9dfc3f13962c65f1b6b9b6ba80394c517729ada50d6302792d9c/) |
| Neshta | User | '6677e07bcccdeb28e532bb030f2ff2e4e39049caf6a1a0f9cd7f50e6d829daac' | [Link](https://bazaar.abuse.ch/sample/6677e07bcccdeb28e532bb030f2ff2e4e39049caf6a1a0f9cd7f50e6d829daac/) |
| Nitrogen | User | '9515602089f0646fc7203ce18473de0dcb71280a9cf0bba991588b2b5f05acb5' | [Link](https://bazaar.abuse.ch/sample/9515602089f0646fc7203ce18473de0dcb71280a9cf0bba991588b2b5f05acb5/) |
| Nokoyawa | User | '259f9ec10642442667a40bf78f03af2fc6d653443cce7062636eb750331657c4' | [Link](https://bazaar.abuse.ch/sample/259f9ec10642442667a40bf78f03af2fc6d653443cce7062636eb750331657c4/) |
| Nova | User | 'e8b02f4683dc4c841454495c018e6427781c830498fecb6c6d9381e6ab77f16d' | [Link](https://bazaar.abuse.ch/sample/e8b02f4683dc4c841454495c018e6427781c830498fecb6c6d9381e6ab77f16d/) |
| Phobos | User | '000db71531e5aa8b30594d305bb3fbce8e2c71f66e2170091ef58b3c1f306f46' | [Link](https://bazaar.abuse.ch/sample/000db71531e5aa8b30594d305bb3fbce8e2c71f66e2170091ef58b3c1f306f46/) |
| Pony | User | '9ed9ed487238d528d158d25f1a6189aa9fbe37f5bba5e40e033e0b0a786119d5' | [Link](https://bazaar.abuse.ch/sample/9ed9ed487238d528d158d25f1a6189aa9fbe37f5bba5e40e033e0b0a786119d5/) |
| Prince | User | '84715cf1d82e5139d39d8aadb9580ba80393dfa0f63fa14974e4f74a3e69752e' | [Link](https://bazaar.abuse.ch/sample/84715cf1d82e5139d39d8aadb9580ba80393dfa0f63fa14974e4f74a3e69752e/) |
| PXJ | User | '9a4e4211f7e690ee4a520c491ef7766dcf1cc9859afa991e15538e92b435f3a1' | [Link](https://bazaar.abuse.ch/sample/9a4e4211f7e690ee4a520c491ef7766dcf1cc9859afa991e15538e92b435f3a1/) |
| Raccoonstealer | User | '0d148218983f96167795e70053b0960d5a501a30b3c45e626e9228af49af2248' | [Link](https://bazaar.abuse.ch/sample/0d148218983f96167795e70053b0960d5a501a30b3c45e626e9228af49af2248/) |
| Rancoz | User | 'c22faf6ed4029051f2138c49cc95ee6f1e55923c28ddff660d404ab79be0f062' | [Link](https://bazaar.abuse.ch/sample/c22faf6ed4029051f2138c49cc95ee6f1e55923c28ddff660d404ab79be0f062/) |
| Ransom | User | '4cae449450c07b7aa74314173c7b00d409eabfe22b86859f3b3acedd66010458' | [Link](https://bazaar.abuse.ch/sample/4cae449450c07b7aa74314173c7b00d409eabfe22b86859f3b3acedd66010458/) |
| Ransomware | User | 'f110528a354648070a7ef4cbc43046ca427adced8aad6c936bdc9e8932e01225' | [Link](https://bazaar.abuse.ch/sample/f110528a354648070a7ef4cbc43046ca427adced8aad6c936bdc9e8932e01225/) |
| Rapid | User | '7d98972d5c78e1d4969da76856d6818942b606c267efa67fd31d39ae77497e9c' | [Link](https://bazaar.abuse.ch/sample/7d98972d5c78e1d4969da76856d6818942b606c267efa67fd31d39ae77497e9c/) |
| Redtrace | User | '1f18d3407038bcd985ff480be2c729b4fd33c36bbffd8bcfb18574ee24b100a9' | [Link](https://bazaar.abuse.ch/sample/1f18d3407038bcd985ff480be2c729b4fd33c36bbffd8bcfb18574ee24b100a9/) |
| Saturn | User | '9e87f069de22ceac029a4ac56e6305d2df54227e6b0f0b3ecad52a01fbade021' | [Link](https://bazaar.abuse.ch/sample/9e87f069de22ceac029a4ac56e6305d2df54227e6b0f0b3ecad52a01fbade021/) |
| Sodinokibi | User | '81689f1be92c8fb7e94fe241441c7eb43cfb77c6d23592b0248566bd709ff2ed' | [Link](https://bazaar.abuse.ch/sample/81689f1be92c8fb7e94fe241441c7eb43cfb77c6d23592b0248566bd709ff2ed/) |
| Targeted | User | '2044bc33cf855b4add30312da75ac8daa408197408da88ecd520d90bdef550ff' | [Link](https://bazaar.abuse.ch/sample/2044bc33cf855b4add30312da75ac8daa408197408da88ecd520d90bdef550ff/) |
| Tcvjuo | User | '56074a1d055957fe372a60582fa9603b4d683a029c0abbc490dcb5c44bc56885' | [Link](https://bazaar.abuse.ch/sample/56074a1d055957fe372a60582fa9603b4d683a029c0abbc490dcb5c44bc56885/) |
| Trigona | User | '7826026ea206063d12d79692ca5f63d879beac9796bb54792f71a2bc8bc16b4c' | [Link](https://bazaar.abuse.ch/sample/7826026ea206063d12d79692ca5f63d879beac9796bb54792f71a2bc8bc16b4c/) |
| Uniwinnicrypt | User | 'e395e96b17910ca97a5e2246829ff18d5c617b3cf8f9fe1672da6d580ece3e61' | [Link](https://bazaar.abuse.ch/sample/e395e96b17910ca97a5e2246829ff18d5c617b3cf8f9fe1672da6d580ece3e61/) |
| Unlockeryourfiles | User | '5847c10d87797bc92bbe204885b79204b491dafe0b591b1277a5ec39e11db532' | [Link](https://bazaar.abuse.ch/sample/5847c10d87797bc92bbe204885b79204b491dafe0b591b1277a5ec39e11db532/) |
| VHDlocker | User | '68ea179770a48ab47976303c9b6db79df2a5213b505fa913201ee6ceabf63a76' | [Link](https://bazaar.abuse.ch/sample/68ea179770a48ab47976303c9b6db79df2a5213b505fa913201ee6ceabf63a76/) |
| Wargame | User | '5bd7bc629a9433583ca8e836776d3d7b0a14fb85ec17e5594ecc1f612bc1e9e6' | [Link](https://bazaar.abuse.ch/sample/5bd7bc629a9433583ca8e836776d3d7b0a14fb85ec17e5594ecc1f612bc1e9e6/) |
| Xorist | User | '6269c641b9c51dc32fec94cc0dc0f7116b1686eec750bd1297133844419cfea1' | [Link](https://bazaar.abuse.ch/sample/6269c641b9c51dc32fec94cc0dc0f7116b1686eec750bd1297133844419cfea1/) |
| Yatron | User | '7910b3f3a04644d12b8e656aa4934c59a4e3083a2a9c476bf752dc54192c255b' | [Link](https://bazaar.abuse.ch/sample/7910b3f3a04644d12b8e656aa4934c59a4e3083a2a9c476bf752dc54192c255b/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
| Koxic | User | 'd2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333' | [Link](https://bazaar.abuse.ch/sample/d2203b6d272d44b7abc66e290c3b79767428168b077a16ded1db0babbe34f333/) |
