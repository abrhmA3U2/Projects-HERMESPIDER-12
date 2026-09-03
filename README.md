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
