# spherical-harmonics-cedec2026

CEDEC 2026 講演「球面調和関数の新展開 — 回転・積分・勾配計算の最新技術 —」の参照実装です．

Reference implementation for the CEDEC 2026 talk *"Recent Advancements in Spherical Harmonics: Rotation, Integration, and Gradient Computation"*.

> **注意 / Disclaimer**
> 本コードは教育・研究目的の参照実装です．可読性を優先しており，最適化・エラー処理は最小限です．
> 動作の正確性を保証せず，使用により生じたいかなる損害についても責任を負いません．
> 本コードは講演内容の確定にあわせて随時更新し，今後加筆・修正していく予定です．  
> This is an educational reference implementation. 
> Correctness is not guaranteed and the authors accept no liability for any damages arising from its use.
> This document is a work in progress and will be updated as the talk is finalized.

---
## 概要 / Overview
本リポジトリは，講演で扱う以下の処理の C++ 実装を提供します．

- 球面調和関数(SH)係数の**回転**
- SH による**積分**(内積・畳み込み)
- SH の**勾配計算**

<!-- TODO: 各項目に1行ずつ、何を実装しているか具体的に書く -->

### 規約 / Conventions

実装上の規約を明示します．他の実装と係数を突き合わせる際はここを確認してください．

| 項目 | 本実装での規約 |
|---|---|
| 次数 / degree | `l`(バンド`0` から `L-1`) |
| 位数 / order | `m`(`-l` から `+l`) |
| 実数/複素数 SH | 実数SHのみ|
| 係数の格納順 | `index = l * l + m` |
| 座標系 | 右手系・Z-Up |

---

## 動作環境 / Requirements

- C++23 以降
- CMake 3.24 以降

<!-- 依存を追加した場合はここに明記 -->

## ビルドと実行 / Build & Run

```sh
git clone https://github.com/vclsu/spherical-harmonics-cedec2026.git
cd spherical-harmonics-cedec2026
cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
./build/tests   # テストの実行
```

## 使い方 / Usage

```cpp
#include"vcl/sh.hpp"

// TODO: 最小の使用例(10行以内)
```

## ディレクトリ構成 / Layout

```
include/sh/      ヘッダオンリーの本体
examples/        最小の使用例
tests/           数値検証テスト
```

## 検証 / Validation

以下のケースで数値的に検証しています．

- 定数関数(`l = 0`)の回転不変性
- 回転の合成則 `R(a) R(b) == R(ab)`
- 解析解が既知の入力との比較

<!-- 実際に入れたテストに合わせて修正 -->

---

## 講演情報 / Talk

- **タイトル**: 球面調和関数の新展開 — 回転・積分・勾配計算の最新技術 —
- **会場・日時**: CEDEC 2026 <!-- 日時・セッション番号 -->
- **スライド**: TBD <!-- 公開後にURLを記載 -->

## 参考文献 / References

- P.-P. Sloan, *Stupid Spherical Harmonics (SH) Tricks*, GDC 2008.
- K. Iwasaki, Y. Dobashi, [Spherical Lighting with Spherical Harmonics Hessian](https://dl.acm.org/doi/10.1145/3721238.3730689), 
  SIGGRAPH 2025, pp. 33:1--33.10, 2025.

## 引用 / Citation
<!--  author       = {著者名},
  title        = {spherical-harmonics-cedec2026: Reference implementation for CEDEC 2026},
  year         = {2026},
  howpublished = {\url{https://github.com/vclsu/spherical-harmonics-cedec2026}}
} -->
```bibtex
@inproceedings{10.1145/3721238.3730689,
author = {Iwasaki, Kei and Dobashi, Yoshinori},
title = {Spherical Lighting with Spherical Harmonics Hessian},
year = {2025},
isbn = {9798400715402},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3721238.3730689},
doi = {10.1145/3721238.3730689},
booktitle = {Proceedings of the Special Interest Group on Computer Graphics and Interactive Techniques Conference Conference Papers},
articleno = {33},
numpages = {10},
keywords = {Spherical Harmonics, Solid Spherical Harmonics, Spherical Harmonics Hessian, Spherical Light},
series = {SIGGRAPH Conference Papers '25}
}

```

## ライセンス / License

MIT License. 詳細は [LICENSE](LICENSE) を参照してください．

## 研究室について / About Us
- [Visual Computing 研究室](https://https://visualcomputing-lab.github.io/)
<!-- 研究室名・大学名・研究室サイトへのリンク・連絡先 -->

- 本実装に関するご指摘・ご質問は [Issues](https://github.com/vclsu/spherical-harmonics-cedec2026/issues) へお願いします．



