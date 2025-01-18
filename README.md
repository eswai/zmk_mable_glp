# ZMK Firmware for MABLE GLP

* ZMK Studio対応
* バッテリーインジケータ対応

## Local build

Github Actionsで自動ビルドされますが、
ローカルでビルドするなら、ZMKをセットアップしてから

```
git clone https://github.com/eswai/zmk_mable_glp.git
git clone https://github.com/caksoylar/zmk-rgbled-widget.git

cd ~/zmk/app

rm -rf build
west build -b seeeduino_xiao_ble -- -DSHIELD=mable_left -DZMK_CONFIG="../../zmk_mable_glp/config" -DZMK_EXTRA_MODULES="../../zmk-rgbled-widget"
cp build/zephyr/zmk.uf2 ~/mable_glp_left.uf2

rm -rf build
west build -b seeeduino_xiao_ble -- -DSHIELD=mable_right -DZMK_CONFIG="../../zmk_mable_glp/config" -DZMK_EXTRA_MODULES="../../zmk-rgbled-widget"
cp build/zephyr/zmk.uf2 ~/mable_glp_right.uf2
```
