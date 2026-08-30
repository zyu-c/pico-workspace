# Raspberry Pi Pico Development Environment

WSL2、VS Code、Docker (Dev Containers) を使用した Raspberry Pi Pico (C/C++ SDK) 向けのマルチプロジェクト開発環境です。

## ディレクトリ構造

```text
pico-workspace/
├── README.md
├── .gitignore
├── docker/
│   └── Dockerfile
├── pico-sdk/
└── projects/
    ├── blink/
    │   ├── .devcontainer/
    │   │   └── devcontainer.json
    │   ├── CMakeLists.txt
    │   └── main.c
    └── (my_project/)
```

## 開発環境のセットアップ

```bash
git clone git@github.com:zyu-c/pico-workspace.git
cd pico-workspace
git clone --recursive https://github.com/raspberrypi/pico-sdk.git
```

## ビルド、書き込み (blink)

VS Codeで `projects/blink` を開きます。

`Ctrl+Shift+P` でコマンドパレットを開き、`Remote-Containers: Reopen in Container` を選択します。

`Ctrl+Shift+P` でコマンドパレットを開き、`CMake: Build` を選択します。

`build` ディレクトリに `blink.uf2` が生成されます。

Raspberry Pi Pico を BOOTSEL ボタンを押しながら USB 接続します。

`blink.uf2` を `RPI-RP2` ドライブにコピーします。

## 新規プロジェクトの作成

`blink` ディレクトリをコピーして新しいプロジェクトを作成します。

```bash
cp -r projects/blink projects/my_project
```