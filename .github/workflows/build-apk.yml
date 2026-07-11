name: Build Naftoon APK
on: [push, workflow_dispatch]
jobs:
  build:
    runs-on: ubuntu-22.04
    steps:
      - uses: actions/checkout@v5
      - uses: actions/setup-python@v6
        with:
          python-version: '3.11'
      - run: |
          sudo apt update
          sudo apt install -y openjdk-17-jdk
          pip install buildozer cython==0.29.36
      - run: |
          cd Naftoon_Android
          yes | buildozer android debug
      - uses: actions/upload-artifact@v4
        with:
          name: Naftoon-APK
          path: Naftoon_Android/bin/*.apk
