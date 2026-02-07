# InsightAnalysis: Mars Equatorial Wave Analysis

火星探査機InSightの気象データ（TWINS）を用い、火星赤道域における大気波動の周期性と物理的性質を解析するためのリポジトリです。
本研究成果は、**JpGU Meeting 2024**にて発表されました。

## 概要
火星の低緯度地域における風速変動を解析し、約7火星日（7-sol）の周期を持つ変動を特定しました。理論的な分散関係（Rossby波・Kelvin波）との比較を通じて、これらの波動の等価深度（Equivalent Depth）や物理的背景を考察することを目的としています。

## 主な機能
- **データ前処理**: InSight TWINS Derived Dataから火星時刻（LMST/LTST）に基づいた疑似的な暦の構築。
- **スペクトル解析**: 10分間隔にリサンプリングした風速データ（u, v成分）からの周期抽出。
- **理論検証**: 赤道ベータ面近似における波動の分散関係式を用いた、観測周期の理論的解釈。

## 使用データ
- **InSight TWINS Derived Data**: [PDS Geosciences Node](https://atmos.nmsu.edu/PDS/data/PDS4/InSight/twins_bundle/data_derived/)
  - 本リポジトリでは、信頼性の高いデータ（Operational Flagsに基づくフィルタリング済み）を使用しています。

## ファイル構成
今後、解析プロセスに沿って以下のJupyter Notebookを追加・整理予定です。

1. `read_file.py`: 大量なCSVデータの統合、MUTC/LTSTへの時刻変換、風速の成分分解（u, v）。
2. `01_Data_Preprocessing.ipynb`: 欠損値処理とリサンプリング（10分平均）のプロセス。
3. `02_Spectral_Analysis.ipynb`: Lomb-Scargle法を用いたパワースペクトルの算出と7日周期の特定。
4. `03_Wave_Visualization.ipynb`: 東西・南北風の位相差の可視化。
5. `04_Theoretical_Validation.ipynb`: ケルビン波・ロスビー波の分散関係式の数値計算と観測結果の照合。

## 解析実績
- **発表タイトル**: Relationship between equatorial waves and 7-sol period wind oscillations in low latitudes on Mars
- **発表学会**: 日本地球惑星科学連合2024年大会 (JpGU 2024)
- **発表者**: 新田 悠翔 (Haruka Nitta), et al.
- **セッション**: [P-PS06] Mars and martian moons
- **リンク**: (https://confit.atlas.jp/guide/event/jpgu2024/subject/PCG21-P07/detail?lang=ja)

## 開発環境
- Python 3.x
- Pandas, NumPy, Matplotlib, SymPy, tqdm
