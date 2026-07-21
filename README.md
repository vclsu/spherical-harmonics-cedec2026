# spherical-harmonics-cedec2026

CEDEC 2026 講演「球面調和関数の新展開 — 回転・積分・勾配計算の最新技術 —」の参照実装です．

Reference implementation for the CEDEC 2026 talk *"New Developments in Spherical Harmonics: Rotation, Integration, and Gradient Computation"*.

> **注意 / Disclaimer**
> 本コードは教育・研究目的の参照実装です．可読性を優先しており，最適化・エラー処理は最小限です．
> 動作の正確性を保証せず，使用により生じたいかなる損害についても責任を負いません．
> This is an educational reference implementation. Correctness is not guaranteed and the authors accept no liability for any damages arising from its use.

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
| 次数 / degree | `l`(バンド、`0` から `L_MAX`) |
| 位数 / order | `m`(`-l` から `+l`) |
| 実数/複素数 SH | <!-- 実数SH / 複素SH --> |
| 正規化 | <!-- orthonormal など --> |
| 係数の格納順 | <!-- index = l*(l+1)+m など --> |
| 座標系 | <!-- 右手系 / 左手系、Y-up など --> |

---

## 動作環境 / Requirements

- C++20 以降
- CMake 3.16 以降
- 外部依存なし(ヘッダオンリー)

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
#include <sh/spherical_harmonics.hpp>

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
- **スライド**: <!-- 公開後にURLを記載 -->

## 参考文献 / References



- P.-P. Sloan, *Stupid Spherical Harmonics (SH) Tricks*, GDC 2008.

## 引用 / Citation

```bibtex
@misc{vclsu_sh_cedec2026,
  author       = {<!-- 著者名 -->},
  title        = {spherical-harmonics-cedec2026: Reference implementation for CEDEC 2026},
  year         = {2026},
  howpublished = {\url{https://github.com/vclsu/spherical-harmonics-cedec2026}}
}
```

## ライセンス / License

MIT License. 詳細は [LICENSE](LICENSE) を参照してください．

## 研究室について / About Us

<!-- 研究室名・大学名・研究室サイトへのリンク・連絡先 -->

本実装に関するご指摘・ご質問は [Issues](https://github.com/vclsu/spherical-harmonics-cedec2026/issues) へお願いします．



