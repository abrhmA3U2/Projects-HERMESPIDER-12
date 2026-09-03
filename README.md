# Projects-HERMESPIDER-12


## HERMESPIDER-12: Autonomous Search & Rescue Platform Design Specification## Overview / プロジェクトの概要
[ENGLISH]
HERMESPIDER-12 is an open-source, multi-legged rescue robot platform designed for exploration and payload delivery in catastrophic environments (e.g., collapsed rebar/concrete debris fields and flooded areas). This repository contains the unified hardware-software co-design documents, including the 36-DoF URDF topology, a 5-core centralized control loop, and sim-to-real binding integration configurations optimized for NVIDIA Isaac Sim (PhysX).
[日本語]
HERMESPIDER-12は、瓦礫が堆積する環境や冠水エリアといった過酷な災害現場での探索・物資補給を想定して設計された、オープンソースの多脚型レスキューロボットプラットフォームです。本リポジトリには、36自由度のURDFトポロジー、5コア集中制御システム、およびNVIDIA Isaac Sim（PhysX）への組み込みに最適化されたシミュレーション結合構成など、ハードウェアとソフトウェアを一体化させた設計仕様が格納されています。
------------------------------
## Technical Specifications / 技術仕様

* 12-Leg Articulated Morphology: 6 legs per side with 180-degree vertical swing capability to maintain continuous locomotion even in cases of structural inversion.
(左右6本ずつの12脚構造。上下180度反転可能で、瓦礫内でのスタックを防止します。)
* Decentralized CPG & 1ms Reflex: Foot-end titanium springs act as mechanical filters to absorb micro-oscillations, coupled with a sub-millisecond 150% torque response loop triggered under critical displacement.
(足端のチタンバネによる物理フィルタ。2cmの臨界変位を検知した際、1ms以内で相補脚へ150%のトルクブーストをかける脊髄反射（CPG）ロジック。)
* Sub-GHz Band Data Compression: A 3-step pipeline (10cm Voxel Space → 2.5D Elevation Mapping → Temporal Delta Integer Encoding) designed to stream telemetry data reliably over low-bandwidth 920MHz ad-hoc mesh networks.
(10cmボクセル化、2.5D高度マップ、時間差分整数エンコーディングによる3段階の圧縮処理。920MHz帯の限られた通信帯域を有効活用します。)
* Automated Triage & Interaction Management: Local speech NLP tokenization for responsive victims and contact force AC/DC separation filters to mitigate structural collision noise while dynamically adjusting interaction timeouts ($T_{\text{delay}}$).
(音声のテキスト化（低帯域送信）、および外殻の圧力変動から静的荷重と動的接触（叩く・掴む行為）を分離するAC/DCフィルタによる対話時間制御。)

------------------------------
## ⚠️ IMPORTANT DISCLAIMER / 免責事項
[ENGLISH]
This project, "HERMESPIDER-12" (including all CAD layouts, PCB designs, firmware, and control source code), is provided "AS IS" for research, educational, and development purposes under the designated open-source license.
Due to the high-risk nature of disaster response and search-and-rescue operations, the authors and contributors make NO warranties, express or implied, regarding the operational safety, reliability, waterproof rating (IP68), or structural integrity of this robot in real-world environments. Under no circumstances shall the authors be liable for any direct, indirect, incidental, or consequential damages, including but not limited to hardware failure, physical injury, or loss of life resulting from the use, modification, or distribution of this project.
[日本語]
本プロジェクト「HERMESPIDER-12」（CADレイアウト、基板設計、ファームウェア、およびすべての制御ソースコードを含む）は、指定されたオープンソースライセンスのもと、研究・開発・教育目的のために「現状有姿」で提供されています。
災害対応および人命捜索救助という高リスクな運用性質上、開発者および貢献者は、実環境における本ロボットの動作安全性、信頼性、防水性能（IP68）、または構造的完全性について、明示的か黙示的かを問わず一切の保証を行いません。本プロジェクトの利用、改変、または配布によって生じた、ハードウェアの破損、身体的負傷、あるいは人命の損失を含むいかなる直接的・間接的損害に対しても、開発者は一切の責任を負わないものとします。実機への適用および運用は、すべて利用者の自己責任において行ってください。
