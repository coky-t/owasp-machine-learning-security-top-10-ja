---
layout: col-sidebar
type: documentation
altfooter: true
level: 4
auto-migrated: 0
document: OWASP Machine Learning Security Top Ten 2023
year: 2023
order: 7
title: ML07:2023 Transfer Learning Attack (転移学習攻撃)
lang: ja
tags:
  [
    OWASP Machine Learning Security Top Ten 2023,
    Top Ten,
    ML07:2023,
    mltop10,
    mlsectop10,
  ]
exploitability: 5
detectability: 1
technical: 5
---

## 説明

転移学習攻撃は攻撃者があるタスクでモデルを訓練した後、別のタスクでモデルを微調節して望ましくない動作をさせることで発生します。


## 防止方法

**訓練データセットを定期的に監視して更新する:** 訓練データを定期的に監視して更新することで、攻撃者のモデルからターゲットのモデルへの悪意のある知識の転送を防止できます。



**安全で信頼できる訓練データセットを使用する:** 安全で信頼できる訓練データセットを使用することで、攻撃者のモデルからターゲットのモデルへの悪意のある知識の転送を防止できます。



**モデルの分離を実装する:** モデルの分離を実装することで、あるモデルから別のモデルへの悪意のある知識の転送を防止できます。
たとえば、訓練環境とデプロイメント環境を分離することで、攻撃者が訓練環境からデプロイメント環境に知識を転送することを防止できます。




**差分プライバシーを使用する:** 差分プライバシーを使用することで、訓練データセット内の個々のレコードのプライバシーを保護し、攻撃者のモデルからターゲットのモデルへの悪意のある知識の転送を防止できます。



**定期的にセキュリティ監査を実施する:** 定期的にセキュリティ監査を行い、システム内の脆弱性を特定して対処することで、転移学習攻撃を特定して防止できます。



## リスク要因

| 脅威エージェント/攻撃手法 | セキュリティ上の弱点 | 影響 |
| :-----------------------: | :------------------: | :--: |
| 悪用難易度: 5 (容易) <br><br> _ML アプリケーション依存: 4_ <br>この攻撃は特に機械学習アプリケーションを標的としており、モデルや組織に重大な損害を与える可能性があります。 <br><br> _ML オペレーション依存: 3_ <br> この攻撃には機械学習操作の知識が必要ですが、比較的容易に実行できます。 | 検出難易度: 1 (困難) <br><br> _侵害されたモデルによって生成された結果は、一見すると正しく、期待結果と一致しているように見えるため、攻撃を検出することは困難かもしれません。_ | 技術的影響: 5 (困難) <br><br> _この攻撃には機械学習に関する高度な技術的専門知識と、訓練データセットや事前訓練済みモデルの完全性を侵害する意欲が必要です。_ |
| 脅威アクター: 悪意のあるアクター。 <br><br> 攻撃手法: 機械学習の知識があり、訓練データセットや事前訓練済みモデルにアクセスできる攻撃者。 | 訓練データセットや事前訓練済みモデルに対する適切なデータ保護対策の欠如<br>事前訓練済みモデルの安全でない保存と共有。 <br><br> 事前訓練済みモデルの安全でない保存と共有。 <br><br> 事前訓練済みモデルと訓練データセットに対する適切なデータ保護対策の欠如。 | 機械学習モデルからの誤解を招く、あるいは不正確な結果。 <br><br> 訓練データセット内の機密情報に対する機密性の侵害。 <br><br> 組織への風評被害。 <br><br> 法律や規制の遵守問題。 |

本チャートは [下記のシナリオ](#scenario1) に基づくサンプルに過ぎないことに注意することが重要です。
実際のリスク評価は各機械学習システムの具体的な状況によって異なります。


## 攻撃シナリオの例

### シナリオ \#1: 悪意のあるデータセットで機械学習モデルを訓練する {#scenario1}

攻撃者は操作された顔画像を含む悪意のあるデータセットで機械学習モデルを訓練します。
攻撃者はセキュリティ企業が人物検証に使用する顔認識システムを標的にしようと考えています。


攻撃者はモデルの知識を標的の顔認識システムに転送します。
標的のシステムは攻撃者が操作したモデルを使用して人物検証を開始します。


その結果、顔認識システムは不正確な予測を行うようになり、攻撃者はセキュリティをバイパスして機密情報にアクセスできるようになります。
たとえば、攻撃者は操作した自分自身の画像を使用して、システムは攻撃者を正当なユーザーとして識別するかもしれません。



## 参考資料
