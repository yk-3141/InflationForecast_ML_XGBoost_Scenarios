
# InflationForecast_ML_XGBoost_Scenarios
日本の金融政策と物価の関係を機械学習で予測するプロジェクト

## プロジェクト概要
日本銀行の政策金利と総務省統計局のCPIデータを用いて、XGBoostモデルによる物価予測を行いました。
複数のシナリオ（現状維持・金利引き上げ・金利引き下げ）を設定し、95%信頼区間を表示することで、
金融政策の変化が物価に与える影響を定量的に評価しています。

## 目的
- 金融政策と物価の関係をデータで検証する
- シナリオ分析による政策判断の参考モデルを構築する

## 使用データ
- 政策金利：日本銀行統計データ（44年分）
- CPI（物価）：総務省統計局データ（月次）
- 特徴量：金利ラグ（1,3,6,12ヶ月）、移動平均、変化率

## 技術
- Python（pandas, numpy, matplotlib）
- モデル：XGBoost
- ハイパーパラメータ最適化：Optuna

## 手法
1. データ取得と前処理（欠損値処理、特徴量生成）
2. XGBoostモデル構築
3. Optunaによるハイパーパラメータ調整
4. シナリオ分析（現状維持・引き上げ・引き下げ）
5. 信頼区間の追加（±1.96 × RMSE）

## 結果
- 評価指標：RMSE = 1.69
- 金利引き上げ → CPIは緩やかに上昇
- 金利引き下げ → CPIは横ばい傾向
- グラフ：複数シナリオの予測線と信頼区間

・全体推移
<img width="1390" height="790" alt="image" src="https://github.com/user-attachments/assets/0b90697e-276d-45dc-b324-4ec854e39204" />
・予測値
<img width="1389" height="790" alt="image" src="https://github.com/user-attachments/assets/f7659dd6-6562-46e9-919b-ca8ac0603223" />
・変化率
<img width="1389" height="790" alt="image" src="https://github.com/user-attachments/assets/2a9a7972-4e8f-4c2b-aee8-a1d2a07e72e6" />




## 実務的な価値
- 金融機関や政策分析で、シナリオベースの予測モデルとして活用可能
- 経済シミュレーションやリスク評価に応用できる
