# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Sébastien Luttringer
# Contributor: Christian Heusel <gromit@archlinux.org>

pkgbase=linux-tools
pkgname=(
  'bootconfig'
  'bpf'
  'cpupower'
  'linux-tools-meta'
  'perf'
  'tmon'
  'usbip'
)
pkgver=7.0.3
pkgrel=2
_srcname=linux-${pkgver}
license=('GPL-2.0-only')
arch=('x86_64' 'loong64')
url='https://www.kernel.org'
options=('!strip' '!lto')
makedepends=('git')
# split packages need all package dependencies set manually in makedepends
# kernel source deps
makedepends+=('asciidoc' 'xmlto')
# perf deps
makedepends+=('perl' 'python' 'python-setuptools' 'slang' 'elfutils' 'libunwind'
  'numactl' 'audit' 'zstd' 'libcap' 'libtraceevent' 'openssl' 'clang' 'llvm-libs' 'libpfm')
# cpupower deps
makedepends+=('pciutils')
# usbip deps
makedepends+=('glib2' 'sysfsutils' 'udev')
# tmon deps
makedepends+=('ncurses')
# bpf deps
makedepends+=('readline' 'zlib' 'libelf' 'libcap' 'python-docutils')
# turbostat deps
# makedepends+=('libcap')
# bpftool
makedepends+=('llvm' 'clang')
# intel-speed-select
# makedepends+=('libnl')
groups=("$pkgbase")
source=(https://cdn.kernel.org/pub/linux/kernel/v${pkgver%%.*}.x/${_srcname}.tar.{xz,sign}
        'usbipd.service'
        'hv_kvp_daemon.service'
        'hv_vss_daemon.service'
        '0001-UPSTREAM-perf-loongarch-Fix-build-failure-with-CONFI.patch'
        '0002-UPSTREAM-LoongArch-Override-arch_dynirq_lower_bound-.patch'
        '0003-UPSTREAM-dt-bindings-interrupt-controller-Add-LS7A-P.patch'
        '0004-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
        '0005-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
        '0006-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
        '0007-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
        '0008-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
        '0009-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
        '0010-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
        '0011-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
        '0012-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
        '0013-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
        '0014-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
        '0015-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
        '0016-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
        '0017-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
        '0018-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
        '0019-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
        '0020-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
        '0021-FROMLIST-LoongArch-improve-logging-of-disabling-KASL.patch'
        '0022-FROMLIST-LoongArch-Make-arch_irq_work_has_interrupt-.patch'
        '0023-FROMLIST-LoongArch-Add-flush_icache_all-local_flush_.patch'
        '0024-FROMLIST-LoongArch-Batch-icache-maintenance-for-jump.patch'
        '0025-FROMLIST-LoongArch-KVM-Add-DMSINTC-device-support.patch'
        '0026-FROMLIST-LoongArch-KVM-Add-dmsintc-inject-msi-to-the.patch'
        '0027-FROMLIST-LoongArch-detect-and-disable-sc.q-if-errati.patch'
        '0028-FROMLIST-ACPI-Enable-FPDT-on-LoongArch.patch'
        '0029-FROMLIST-LoongArch-add-spectre-boundry-for-syscall-d.patch'
        '0030-FROMLIST-LoongArch-Show-CPU-vulnerabilites-correctly.patch'
        '0031-FROMLIST-dmaengine-loongson-New-directory-for-Loongs.patch'
        '0032-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
        '0033-FROMLIST-dmaengine-loongson-loongson2-apb-Convert-to.patch'
        '0034-FROMLIST-dmaengine-loongson-loongson2-apb-Simplify-l.patch'
        '0035-FROMLIST-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
        '0036-FROMLIST-dmaengine-loongson-New-driver-for-the-Loong.patch'
        '0037-FROMLIST-LoongArch-add-i2c-clocks-and-clock-div-para.patch'
        '0038-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
        '0039-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
        '0040-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
        '0041-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
        '0042-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
        '0043-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
        '0044-LOONGSON-LoongArch-Align-FPU-register-state-to-32-by.patch'
        '0045-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
        '0046-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
        '0047-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
        '0048-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
        '0049-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
        '0050-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
        '0051-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
        '0052-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
        '0053-AOSCOS-loongarch-fix-DMA-address-offset.patch'
        '0054-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
        '0055-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
        '0056-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
        '0057-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
        '0058-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
        '0059-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
        '0060-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
        '0061-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
        '0062-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
        '0063-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
        '0064-AOSCOS-gpio-loongson-64bit-Add-LS7A-GPIO-interrupt-s.patch'
        '0065-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
        '0066-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
        '0067-FROMLIST-perf-annotate-Use-jump__delete-when-freeing.patch'
        '0068-BORE-linux7.0-rc2-bore-6.6.3.patch'
        '0069-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
validpgpkeys=(
  'ABAF11C65A2970B130ABE3C479BE3E4300411886'  # Linus Torvalds
  '647F28654894E3BD457199BE38DBBDC86092693E'  # Greg Kroah-Hartman
)
sha256sums=('0bedadbf5788693ddebbcc913c893f1a97349af79ddde7144c2a80b401959f1c'
            'SKIP'
            '2e187734d8aec58a3046d79883510d779aa93fb3ab20bd3132c1a607ebe5498f'
            'b1315cb77a35454e1af9172f821a52e2a0cb18561be05a340d21cf337b01ae61'
            '2d5e2f8d40b6f19bf2e1dead57ca105d72098fb0b418c09ff2e0cb91089710af'
            'b3d5f53c323400ac98a7c26ca498c95053d0a21a052f6436dfc37791d7d7460d'
            '5fef666c7096a01562e0a931c74a350143b32fe927d69d87cbd7855b2b4f3424'
            '86cc39541a08029c98da912f0aac33107e7fde57e8abc6dfbaf4cb5f69fa8dfd'
            'dc3fab891b707677d2b7b917132160d0fd70d1090a7c3a1bbdf34a8fe948c5fb'
            '931dce9e575b6fca5ab16e95ff1e333ede2adaeb7e800de1a1aff0e922650b8d'
            '545dc02274f813a4966e673b7916125c81ddf7b5cbb40a558bc8c2f0aacc775c'
            'fd36dfa25fa83cc7db52e13ccce659304a7b7a0daa4101e120d96e676b1e514e'
            'de1c0080c430fbdce9bf1ecaa40dbb41770184d5a807fd27bac452df85d91e7e'
            'f679141cecaf1bbe8956e2b33ade9a04a205ba427cd736cda1976d951b6d3e60'
            'abd6eb486c78c74286e9133cfcdd3cae989f45257e09f44185dfe135477bbaa1'
            '71908dab64f5aafd9b97d7257b0df7b95d21b7526d0a6e422bf9996a22634dd5'
            '6bc93efade1de58a9a3a3ebcc360b671fe51f61cac3202e8202cb10a57e60489'
            'be0720001d18f1bccb8fe1ba06b028cf033195321dd0a024a14decf8fab813ef'
            'aa171256fe3b9ace881c202706125297df8d2a11c32c0729bf83bccd7eb40349'
            'eef54d24781127e394db0b8a4c8ae95fa3516eaa89d746123eca2baa247f2abe'
            'ab693a3b582fc59aa467224aa835db22b4440736921a63820ac75de3f85c2f89'
            'a2d89196b2a269495e702a7de8b96d3f08ee633b55954688c91ae82640433b69'
            '094c7d0f03f0128a5956573d6444735559c0a8ac8565acf6c351998471a246c6'
            'd06c1e78c1b12fbf6dbbd5ac1b67f8c1b1a221a3eace4584a83b8d752a211b9f'
            '9bcbfa9f87e5d2dd4c912c9a5ecb817b1b1ab55165f70158b08655c423c3328f'
            '02d5e2dc76f221a14cb56850d94c70670aa0569abcd07fda543c829062f5d3c7'
            'd8093e79f81bf7258bffdb918c4ab078433fbe44ec9d288ca569ac9acb34962f'
            '6cb53406da17df1a0c748ed4ffa58fddda42f944a21db934f26694c92a2a4d27'
            '248c47a2f2ce1fd7b0f62299fe0c10b87f5dfc41a4d06cba81aef08dcc8631d0'
            'e0d40b8ffabad9ca271bc183d3e6e4fc27f48c4e27d6c92c894c6dc8698aa712'
            'ce0b12923f58283ce9f97d43d6a961369f41062c3993c550b298aa30c2f69b95'
            '55fcf9499d5175f0e266275b7db0b07c3d452608f286771655133ec18269567b'
            'ba98a31f4dbf3bfa9761cbbfd23d6faae16b98b6546352cd52b3e2484bbd6faa'
            '1f080b27104481092a6b78ab3dda8be3820286963088896abfbf2ca5a6c983f5'
            'b588ab235eb5736c193f0bdbd819ef3bdf15b5573daa25c62e7cbbaca59c07d5'
            '5968c081ecf7958a3ce5ec74a06c05daac2bcf616c337ccfdc5ce80f69bc8b29'
            '9ee1c9b556ed3aa68e02d29ffcfc3fb3fee451efd7279bf3baa1bb1f21fb04b0'
            '56618af1c9fa7514f0e65c26916dd35ed0d311e782793e70a7d93c7cb0a56414'
            '31d4b07b4464849b980cbae6adae32d1e74f9a4a51b6bc3aec455658da6e8176'
            '68c144485a9420cc123729e61a3a91091def191777fc3090bc65b24c8f71266f'
            '18eec53837e3687312928eb8d98c1625f268e25518c23c57c93d01ce47f94050'
            '7d22fab43852be0355ca51ac7e9f3665c6e7c7cfde4d0f37648bbd3dfa739b2b'
            'bd76cebb019ecf4fcb2b0c811e9cbaf1c06a73b6916cfbc3d70ff466ec3bc1c4'
            'ad424aaf4ca2b73630ccd58db8b732a39626ea5cc6473e1ce7fa0f1183ed114b'
            '7f839fb84df99fb28bcc9c2bc67d16f4fdb7c19f3076b2e5d1cc4085f4a07120'
            'ed190a52d99f2c98e06392de05285d9e5638b9365cd72b9e62e5e425c31bb662'
            'a3ea4b908fe3450d84a4487b0ec89fe5264f2dd3b8c70c7b9df62c7d0f3f661a'
            'b434a7d6fcc2e809415f0b182431af2d5d6269c307e44f5e4c443cb3db3d267c'
            'a1d8de0bf78eeb3c5cc228764c80c228dcb8d42e532ab6131c101c85377cd174'
            'a3e007ece84059e4cb17dae849faeacebbe6a41657c305e3d52a7bb377a2046b'
            'fb8c7c513af4c8b454a2cf5def53ed50a28f4671249b8194a00a5abcdc232b8b'
            'd192469f625eef0741efe6083739b7ac52368a4fc63cd7cc6d1e70a9741cf2a4'
            '9462b62670e23787c2e3a444f0c5302f71be8d585f3bfd36e88cc992f11e0f01'
            '5f821aec55c3f9ca78f1fea15f02412bf2c87bc6d4d88bfa7bd5acd425fdb0ef'
            '764e32a9e2307e6700e817272fc385fab2f63c3d0b3fa8d05406e9cf2992d417'
            '0f1ad2700251a49519cf928fee3ad7edc8ad6aaf7b30d51c31fa690c9d2585f0'
            '7e130f71fa7e75f5dcd3fbc4711971bae10b3cca4d518910eba6c41da2defb55'
            '4751b4edd278d19ac2234acfb94469609c4c078d0e35816dffc82aeb959084c2'
            '10992d65968819a708cd9d38d34601ce1620e08f5c62bffe7b033d93b58090e8'
            '063a1b393eb290d026f34eedfcef6ced5c3a2fbe01f8e0309bc7e2fdea188966'
            '1e568deb37459211ed5008b1bff44f21b858263d7afb2f7bf9fc7de5a3170c37'
            'e7030df08bc6e68ca68978eb83c607088110bd28cfc5a06ccd0e077f00dc30c1'
            '5bcb57621b8882f1d9a6412c8315e7b55926a386dca9daf10a8d99984cb24053'
            'f4b33981d10e0ceee204ecb990a263844e9c6e8bf277895b84aadbbb04958389'
            'f74c755de99b5d801dba3916c89d060bd2395cb13b88a007eeff7b52deee8652'
            '4bbf841b458d4f7d1701d4a38f322ad9ec950f16681e89d178779b470c46383b'
            '057282c7b2d06452003a04ac06548f3fe60e6bb27791eaf7e334fa9166bdc33b'
            '84ab92776f60dce10f83687cc2b5e224bcd87dcd3ec54410b4530b893d0dc3c1'
            '312abf7717249667e442761c28ce39bae45d799538d5e492949329553cadacfe'
            'edd98706a419c6256e75d9a58ff6aff20fe2a9111d23133c8d53596abe35d9ba'
            'f4397430fac5c30debeeea6f9b3cc910b8d287408bd2066ff9f0545aa3d50489'
            '9cbbd02daa12d373e0e84485349431dd8b72c26b09561ab80fba06437c6fd8e4'
            'fbae1b74d43161ed1eef68bc569b1e4da531c8d9e79f1006d6e3f8f50eca606f'
            'b9483d9029311901cd59e5a8550760ee7e930aec006e96c162f228039dbc7608')

prepare() {
  cd "$_srcname"

  # apply patch from the source array (should be a pacman feature)
  local src
  for src in "${source[@]}"; do
    src="${src%%::*}"
    src="${src##*/}"
    src="${src%.xz}"
    [[ $src = *.patch || $src = patch-* ]] || continue
    echo ":: Applying patch $src"
    patch -p1 -N -i "$srcdir/$src"
  done
  # force our perf version
  cat > tools/perf/util/PERF-VERSION-GEN << EOF
#!/bin/sh
echo '#define PERF_VERSION "$pkgver-$pkgrel"' > "\${1:-.}"/PERF-VERSION-FILE
EOF
}

build() {
  export CFLAGS="${CFLAGS} -Wno-error=discarded-qualifiers"

  echo ':: perf'
  pushd "$_srcname"/tools/perf
  make -f Makefile.perf \
    prefix=/usr \
    lib=lib/perf \
    perfexecdir=lib/perf \
    WERROR=0 \
    NO_SDT=1 \
    BUILD_BPF_SKEL=1 \
    PYTHON=python \
    NO_LIBLLVM=1 \
    PYTHON_CONFIG=python-config \
    LIBPFM4=1 \
    DESTDIR="$pkgdir"
  popd

  echo ':: cpupower'
  pushd "$_srcname"/tools/power/cpupower
  make VERSION=$pkgver-$pkgrel
  popd

  # Use a "multi-line comment" to keep patch from rotting
  : <<COMMENT_SEPARATOR
  echo ':: x86_energy_perf_policy'
  pushd "$_srcname"/tools/power/x86/x86_energy_perf_policy
  make
  popd
COMMENT_SEPARATOR

  echo ':: usbip'
  pushd "$_srcname"/tools/usb/usbip
  # Fix gcc compilation
  sed -i 's,-Wall -Werror -Wextra,-fcommon,' configure.ac
  ./autogen.sh
  ./configure --prefix=/usr --sbindir=/usr/bin
  make
  popd

  echo ':: tmon'
  pushd "$_srcname"/tools/thermal/tmon
  make
  popd

  : <<COMMENT_SEPARATOR
  echo ':: turbostat'
  pushd "$_srcname"/tools/power/x86/turbostat
  make
  popd

  echo ':: hv'
  pushd "$_srcname"/tools/hv
  CFLAGS+=' -DKVP_SCRIPTS_PATH=\"/usr/lib/hypervkvpd/\"' make
  popd
COMMENT_SEPARATOR

  echo ':: bpf'
  pushd "$_srcname"/tools/bpf
  # doesn't compile when we don't first compile bpftool in its own directory and
  # man pages require to be also launch from the subdirectory
  make -C bpftool all doc
  # runqslower, require kernel binary path to build, skip it
  make -W runqslower
  popd

  echo ':: bootconfig'
  pushd "$_srcname"/tools/bootconfig
  make
  popd

  : <<COMMENT_SEPARATOR
  echo ':: intel-speed-select'
  pushd "$_srcname"/tools/power/x86/intel-speed-select
  make
  popd

  echo ':: kcpuid'
  pushd "$_srcname"/tools/arch/x86/kcpuid
  make
  popd
COMMENT_SEPARATOR
}

package_linux-tools-meta() {
  pkgdesc='Linux kernel tools meta package'
  groups=()
  depends=(
    'bootconfig'
    'bpf'
    'cpupower'
    'perf'
    'tmon'
    'usbip'
  )
  conflicts=(
    'acpidump'
  )
}

package_perf() {
  pkgdesc='Linux kernel performance auditing tool'
  depends=('glibc' 'perl' 'python' 'slang' 'elfutils' 'libunwind' 'binutils'
           'numactl' 'audit' 'coreutils' 'glib2' 'xz' 'zlib' 'libelf' 'bash'
           'zstd' 'libcap' 'libtraceevent' 'openssl' 'libsframe.so' 'llvm-libs' 'libpfm')

  cd "$_srcname"/tools/perf
  make -f Makefile.perf \
    prefix=/usr \
    lib=lib/perf \
    perfexecdir=lib/perf \
    EXTRA_CFLAGS=' -Wno-error=bad-function-cast -Wno-error=declaration-after-statement -Wno-error=switch-enum -Wno-error=discarded-qualifiers -Wno-error=aggressive-loop-optimizations -Wno-error=unterminated-string-initialization' \
    NO_SDT=1 \
    BUILD_BPF_SKEL=1 \
    PYTHON=python \
    NO_LIBLLVM=1 \
    PYTHON_CONFIG=python-config \
    DESTDIR="$pkgdir" \
    LIBPFM4=1 \
    install install-python_ext
  cd "$pkgdir"
  # add linker search path
  mkdir "$pkgdir/etc/ld.so.conf.d"
  echo '/usr/lib/perf' > "$pkgdir/etc/ld.so.conf.d/$pkgname.conf"
  # move completion in new directory
  install -Dm644 etc/bash_completion.d/perf usr/share/bash-completion/completions/perf
  rm -r etc/bash_completion.d
  # no exec on usr/share
  find usr/share -type f -exec chmod a-x {} \;
}

package_cpupower() {
  pkgdesc='Linux kernel tool to examine and tune power saving related features of your processor'
  backup=('etc/default/cpupower-service.conf')
  depends=('glibc' 'bash' 'pciutils')
  conflicts=('cpufrequtils')
  replaces=('cpufrequtils')
  install=cpupower.install

  pushd "$_srcname"/tools/power/cpupower
  make \
    DESTDIR="$pkgdir" \
    confdir='/etc/default/' \
    sbindir='/usr/bin' \
    libdir='/usr/lib' \
    libexecdir='/usr/lib/systemd/scripts' \
    mandir='/usr/share/man' \
    docdir='/usr/share/doc/cpupower' \
    install install-man
  popd
}

package_x86_energy_perf_policy() {
  pkgdesc='Read or write MSR_IA32_ENERGY_PERF_BIAS'
  depends=('glibc')

  cd "$_srcname"/tools/power/x86/x86_energy_perf_policy
  install -Dm 755 x86_energy_perf_policy "$pkgdir/usr/bin/x86_energy_perf_policy"
  install -Dm 644 x86_energy_perf_policy.8 "$pkgdir/usr/share/man/man8/x86_energy_perf_policy.8"
}

package_usbip() {
  pkgdesc='An USB device sharing system over IP network'
  depends=('glibc' 'glib2' 'sysfsutils' 'systemd-libs')

  pushd "$_srcname"/tools/usb/usbip
  make install DESTDIR="$pkgdir"
  popd
  # module loading
  install -Dm 644 /dev/null "$pkgdir/usr/lib/modules-load.d/$pkgname.conf"
  printf 'usbip-core\nusbip-host\n' > "$pkgdir/usr/lib/modules-load.d/$pkgname.conf"
  # systemd
  install -Dm 644 usbipd.service "$pkgdir/usr/lib/systemd/system/usbipd.service"
}

package_tmon() {
  pkgdesc='Monitoring and Testing Tool for Linux kernel thermal subsystem'
  depends=('glibc' 'ncurses')

  cd "$_srcname"/tools/thermal/tmon
  make install INSTALL_ROOT="$pkgdir"
}

package_turbostat() {
  pkgdesc='Report processor frequency and idle statistics'
  depends=('glibc' 'libcap')

  cd "$_srcname"/tools/power/x86/turbostat
  make install DESTDIR="$pkgdir"
}

package_hyperv() {
  pkgdesc='Hyper-V tools'
  depends=('glibc')

  cd "$_srcname"/tools/hv
  make install DESTDIR="$pkgdir" sbindir=/usr/bin libexecdir=/usr/lib
  for _p in hv_kvp_daemon hv_vss_daemon; do
    install -Dm644 "$srcdir/$_p.service" "$pkgdir/usr/lib/systemd/system/$_p.service"
  done
}

package_bpf() {
  pkgdesc='BPF tools'
  depends=('glibc' 'readline' 'zlib' 'libelf' 'libcap' 'zstd' 'llvm-libs' 'binutils' 'libsframe.so')

  cd "$_srcname"/tools/bpf
  # skip runsqlower until disabled in build
  make -W runqslower_install install prefix=/usr DESTDIR="$pkgdir"
  # fix bpftool hard written path
  mv "$pkgdir"/usr/sbin/bpftool "$pkgdir"/usr/bin/bpftool
  rmdir "$pkgdir"/usr/sbin
  # install man pages
  make -C bpftool doc-install prefix=/usr/share DESTDIR="$pkgdir"
}

package_bootconfig() {
  pkgdesc='Apply, delete or show boot config to initrd'
  depends=('glibc')

  cd "$_srcname"/tools/bootconfig
  install -dm755 "$pkgdir/usr/bin"
  make install DESTDIR="$pkgdir"
}

package_intel-speed-select() {
  pkgdesc='Intel Speed Select'
  depends=('libnl')

  cd "$_srcname"/tools/power/x86/intel-speed-select
  make install DESTDIR="$pkgdir"
}

package_kcpuid() {
  pkgdesc='Kernel tool for various cpu debug outputs'
  depends=('glibc')

  make BINDIR=/usr/bin HWDATADIR="/usr/share/misc" DESTDIR="$pkgdir" -C "$_srcname"/tools/arch/x86/kcpuid install
}

# vim:set ts=2 sw=2 et:

