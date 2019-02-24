# aosp_nethunter-kernel_oneplus_msm8994

Clone repo:
git clone https://github.com/xNNism/aosp_nethunter-kernel_oneplus_msm8994
cd aosp_nethunter-kernel_oneplus_msm8994

In your shell export the following environment variables:
export ARCH=arm64
export SUBARCH=arm64
export CROSS_COMPILE=/PATH/TO/TOOLCHAIN/aarch64-linux-android-4.9/bin/aarch64-linux-android-

In the Kernel root execute:

make clean

make nethunter_defconfig

make

mkdir out/
cp arch/arm64/boot/arch/arm64/boot/Image.gz-dtb out/

make INSTALL_MOD_PATH=out/ modules
make INSTALL_MOD_PATH=out/ modules_install

Build with aarch64-linux-android-4.9 toolchain:
git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9
