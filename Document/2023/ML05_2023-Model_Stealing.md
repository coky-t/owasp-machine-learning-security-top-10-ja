---

document: OWASP Machine Learning Security Top Ten 2023
year: 2023
order: 6
title: ML05:2023:Model_Stealing (モデル盗用)
lang: ja
author:
contributors:
tags: OWASP Top Ten 2023, Top Ten, ML05:2023
exploitability: 4
prevalence:
detectability: 3
technical: 4
redirect_from:

---

|                                                                脅威エージェント/攻撃手法                                                                     |                                                         セキュリティ上の弱点                                                      |                                                                                                影響                                                                                                  |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|             悪用難易度: 4 (Effort required to exploit this weakness is moderate)<br>ML アプリケーション依存: 4<br>ML オペレーション依存: 3                   |                             検出難易度: 3 <br>(Detection of this attack is moderately challenging)                                |                                                                       技術的影響: 4 <br>(Moderate technical skill required)<br>                                                                      |
| エージェント/攻撃手法: This refers to the entity that carries out the attack, in this case, it is an attacker who wants to steal the machine learning model. | Unsecured model deployment: The unsecured deployment of the model makes it easier for the attacker to access and steal the model. | The impact of a model theft could be both on the confidentiality of the data used to train the model and the reputation of the organization that developed the model.<br>Confidentiality, Reputation |

It is important to note that this chart is only a sample based on scenario below, and the actual risk assessment will depend on the specific circumstances of each machine learning system.



**説明:**

Model stealing attacks occur when an attacker gains access to the model's parameters.


**攻撃シナリオの例:**

シナリオ: Stealing a machine learning model from a competitor

A malicious attacker is working for a competitor of a company that has developed a valuable machine learning model. 
The attacker wants to steal this model so that their company can gain a competitive advantage and start using it for their own purposes.



The attacker executed this attack by reverse engineering the company's machine learning model, either by disassembling the binary code or by accessing the model's training data and algorithm. 
Once the attacker has reverse engineered the model, they can use this information to recreate the model and start using it for their own purposes. 
This can result in significant financial loss for the original company, as well as damage to their reputation.





**防止方法:**

Encryption: Encrypting the model's code, training data, and other sensitive information can prevent attackers from being able to access and steal the model.



Access Control: Implementing strict access control measures, such as two-factor authentication, can prevent unauthorized individuals from accessing and stealing the model.



Regular backups: Regularly backing up the model's code, training data, and other sensitive information can ensure that it can be recovered in the event of a theft.



Model Obfuscation: Obfuscating the model's code and making it difficult to reverse engineer can prevent attackers from being able to steal the model.



Watermarking: Adding a watermark to the model's code and training data can make it possible to trace the source of a theft and hold the attacker accountable.



Legal protection: Securing legal protection for the model, such as patents or trade secrets, can make it more difficult for an attacker to steal the model and can provide a basis for legal action in the event of a theft.




Monitoring and auditing: Regularly monitoring and auditing the model's use can help detect and prevent theft by detecting when an attacker is attempting to access or steal the model.



**参考資料:**
