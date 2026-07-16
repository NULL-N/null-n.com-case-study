# 技術ディレクション / Technical direction

これは完成した実装のソースコードではなく、NULL-Nが作品に対して行った技術的な
判断を読むための記録です。

**EN**<br>
This is not the source of the finished implementation. It is a record for
reading the technical direction NULL-N applied to the work.

## 音を背景にしない / Do not turn music into background

原曲を複数の層として扱い、訪問者の位置によって相対的な存在感を変えることで、
聴く行為をインタラクションに変えます。ここで重要なのは、訪問者へ作者性を渡す
ことではなく、NULL-Nが作った曲の内部へ一時的に入れることです。

**EN**<br>
The original composition is treated as multiple layers whose relative presence
changes with the visitor’s position. Listening becomes interaction. This does
not hand authorship to the visitor; it lets them enter, temporarily, the inside
of a composition made by NULL-N.

## 速さと見た目を両立させる / Keep performance and appearance together

背景表現は、WebGPUが利用できる環境ではボリューメトリックな描画を優先します。
利用できない環境、弱いアダプタ、初期化やデバイスの失敗時には、より軽い描画経路へ
退避します。これは見た目を捨てるためではなく、どの環境でも作品の場を成立させる
ための判断です。

**EN**<br>
The background prefers volumetric rendering where WebGPU is available. On an
unsupported environment, a weak adapter, or initialization and device failure,
it retreats to a lighter path. This is not a decision to abandon the look; it
keeps the work’s field intact across real environments.

## 配信境界を設計する / Design a delivery boundary

原音は公開ソースに含めず、配信に必要な最小限の経路だけを用意します。これは
複製を不可能にする約束ではありません。ブラウザ再生を前提にしたうえで、原音を
静的な公開物から分けて扱うための現実的な境界です。

**EN**<br>
Original audio does not live in the public source. Only the minimum delivery
path is designed. This does not promise to make copying impossible; it is a
practical boundary that treats original audio separately from static public
material while accepting browser playback as the premise.

この境界は運用の中で一段進みました。復号鍵は配布物から消え、時間窓ごとに
失効する短命の鍵に置き換わり、音源は分割チャンクの個別暗号化で届きます。
複製を不可能にする約束ではないことは変わりません。変わったのは、鍵と道具が
腐る速さです。

**EN**<br>
The boundary has since advanced one step in operation. The decryption key is
gone from everything that ships, replaced by short-lived keys that expire with
their time window, and the audio arrives as separately encrypted chunks. The
promise is unchanged — copying is not made impossible. What changed is how
fast keys and tooling rot.

## AIとの反復 / Iterating with AI

AIは実装の相手ですが、作品が何をすべきかを決めるのはNULL-Nです。挙動、
性能、視覚的な落ち着き、音との関係を観察し、ずれを直し、受け入れ基準を更新する。
その反復が、AIを使うことと、作品を作ることを同じものにしないための工程です。

**EN**<br>
AI is an implementation partner, but NULL-N decides what the work should do.
Behavior, performance, visual calm, and the relationship to sound are observed;
drift is corrected and acceptance criteria are updated. That iteration keeps
using AI from becoming the same thing as making the work.
