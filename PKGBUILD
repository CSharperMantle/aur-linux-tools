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
pkgver=6.19.14
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
        '0001-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
        '0002-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
        '0003-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
        '0004-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
        '0005-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
        '0006-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
        '0007-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
        '0008-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
        '0009-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
        '0010-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
        '0011-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
        '0012-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
        '0013-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
        '0014-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
        '0015-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
        '0016-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
        '0017-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
        '0018-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
        '0019-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
        '0020-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
        '0021-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
        '0022-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
        '0023-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
        '0024-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
        '0025-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
        '0026-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
        '0027-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
        '0028-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
        '0029-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
        '0030-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
        '0031-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
        '0032-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
        '0033-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
        '0034-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
        '0035-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
        '0036-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
        '0037-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
        '0038-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
        '0039-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
        '0040-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
        '0041-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
        '0042-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
        '0043-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
        '0044-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
        '0045-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
        '0046-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
        '0047-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
        '0048-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
        '0049-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
        '0050-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
        '0051-AOSCOS-loongarch-fix-DMA-address-offset.patch'
        '0052-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
        '0053-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
        '0054-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
        '0055-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
        '0056-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
        '0057-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
        '0058-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
        '0059-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
        '0060-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
        '0061-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
        '0062-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
        '0063-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
        '0064-BORE-linux6.19.7-bore-6.6.2.patch'
        '0065-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
        '0066-BACKPORT-FROMLIST-perf-annotate-Use-jump__delete-whe.patch'
)
validpgpkeys=(
  'ABAF11C65A2970B130ABE3C479BE3E4300411886'  # Linus Torvalds
  '647F28654894E3BD457199BE38DBBDC86092693E'  # Greg Kroah-Hartman
)
sha256sums=('cde8bf6739be4a0777fedbbba5330b8188c55680c45a922a4dfa289cbec6f185'
            'SKIP'
            '2e187734d8aec58a3046d79883510d779aa93fb3ab20bd3132c1a607ebe5498f'
            'b1315cb77a35454e1af9172f821a52e2a0cb18561be05a340d21cf337b01ae61'
            '2d5e2f8d40b6f19bf2e1dead57ca105d72098fb0b418c09ff2e0cb91089710af'
            'bf62a0d82e4c68425007ba3961331e4ae1ead9ed8027201df4215a8eb9af649e'
            '86172e4e56f60ab801d3399271b4fbb4ebd809ed6a303cb0df58da5fa0cf4f24'
            '32bc50f98b602f2e523ea1ef602764713f5b24c3920583fa4db1d34980655dc2'
            '48462d69ba8cd1ac400d9d9478b24eb984d5b9c9c23732218b84416a6ec751cd'
            'c13c8c9671a6f13113208ebca8b04eda736f20ea552057452c74a3d3852f1426'
            '6858ef4d1bc129a555387018a329dfabd6ec08f3ba05c9dae29d346fa6529940'
            'df7deee366a891b48cab7d64b38613605dd7d768bf91c033f60300c5f92fb86c'
            '4bfa67ba94a1bf93e12b94685517f2439f94a3bf570bfb6a8597a2a45cd20c5a'
            '095c78325d9ce6b04a7c4a9872da14b32923eb394796980306d571bf15b21283'
            'db402fd59253ba24d87004aec10f849a6c3371274adcd77dfa04135633db3b02'
            '9824c90ea835525202f11678873b53ca52e2d17582453046bd6ddc55e3091c99'
            'ce6cef0631ae3455fc2ef43f88222726ad6d24f49bfa5dae961a8080ba2a1c06'
            '1320e875e94baa23c898960f96a1237a5ff54f043e5d099c3a812e9b082c4e78'
            'a390197814c093ce0e9ecd1647f63d878121dc7a70e9eca21bdfc3d3bcefecbd'
            'd2c2948025d428f6f03379f56eecdc4c6ec127156351ac0eec4f2a734de02b24'
            'ced39e2bbac5d06f7c31608aa813b790d5b6e52ed159abcf1c936f3cb330558a'
            '96d3acca6c1c4c76e52c2f532cc049ba778cbcc3e68246890cafa0c5d997ccec'
            '21f4a89769f903158ee91320ba81110f13f0bc2cb90a923150aa0515e432da62'
            'f4ca2a12f9df39fbda7a682730689aa33985b7d3308d2f6edf53672d0bfe27e3'
            '6c2ec9b9931aa30cee5101c7dd9dffeb90b586fbfe8f57c50d2b219cd84fbf8a'
            '642183f34d8e3096525ed1be5588fa59ca1e99cb8ba263cf7516fdb8cdf0670e'
            '98a95f41f2e21f1747283e674c8272de53011e958cda266083e133ab1d2c7a86'
            '2eb413deebfb11ea4580fff1368bb0d01aa45ca784d78549fb00ca8483d4b68f'
            '4145909ebf9cc709f5ceceb7bfeb1411eed8b19e967861b3bb05c62f4223ec2a'
            '565ce09497a53a326f55e48febc3adcd29bd7841b3314b78c5f9db3f651efa43'
            '68fe233fc2be0dd029e77ea0d41e5d1be5c9824f9027b43ac6e489677d87ecc9'
            'e3a49283efbeb3c7ae25e3c342f3e0585c0a61165056360d7afb72de95c97985'
            '836757c2d0f30f5c889169878ffc41fee6e61cee91f790856c4a1a58c3ddbd8c'
            'feea6653e6a1debe738807dbf051f041db3163ca59e807d94dd51b2d1c46f80f'
            'f1a6b212762a1f46e5f28ddf60803bfe0a544d18bc759abd504a392fda31a2ae'
            'ff96669475b1cbc0f7f793c92e0fd6729057a69e7f6c9be2c09ec0897ef6d196'
            'fddfd97e5e822683530d83576c0a41320770087c00c2b4fee0ab173b44f98c78'
            'ffe095d9f6c68bd6d13e4104cf5245e4dd8055c95bb748fd1f1879fa5b455854'
            '1d850746cfc0adf0d3650091f5cb79db0766b0d5d75fabae920eeedcbe796643'
            '49affe80d776dc38451febc0823bba8e04185475b488778ec0b9638ffd981858'
            'cfe9587a965ebf3a895b8c495bec189c8ec16b074bf8a87250a270833a0a01ca'
            '11cf96eb6f0cfec3f21b4b406016afabc3a1d2937e02d1f8c86c7efefd2c229e'
            '7d1735073958984c51720b5b3a8baf00fe2c814720b2e68a07525a92bf3d41db'
            '0cc4ef0732da57c8e5cfb2a59faba3c3f9ac6d48f584814f4a239ac2ccd20db8'
            'e407d9f37d45a6230d2da48b0b266afb1801b79eb59c8fe95d1ea84a192a99f1'
            'd4dfb2e55ba28c94bc50e2780ebf52322e512cf29231d0cced8f890060d149bd'
            'a24100c2ea987cac7ced4ffd13c80b65a4967e79c557e02f3e561daa5929a5f5'
            '6160f2141f39bf24bf505117d52825591f6a06cda9b304ec7335d0b7baa804fc'
            '2b3140fee4230f53d18764c9b4832b9adbb28e14531e3d5e76a17a86ba9d59e6'
            '049f1bfdcb3473d3f6dc725389c7263910f422ff16e9bcdf65c129eed824004b'
            'cc1aa8c3a499ab4e66b64c79537866d875f5ca3771f3bd658a081c794bc78562'
            '5732402ec1de6565d85d64306a0e60585f8865d09c4967e22bdbea25b6f5b317'
            'd744ee2105eaeeaae5baad63fd4c66fc91a2127701a06a009fa0c7a526ade0d7'
            'ded369329d1eabe85b9f819f4defdfe9431d426e69d0e24659b1d9413801b920'
            '3dcdcd32fc6b0f16eb2d29cf4abaa44d6ce242953f3e50b9c0b2c922255133a7'
            'a6c0073ea7d50f51ae32ac4e008a9497ae4adbeafed0ceb7aa6bea366b324f9f'
            '6419f9157dea131e303fb0d0756ac6e1ebe024b2e69fe5be4f49184c313e1373'
            '03b16d04055eb6c745052ea7a2d161b8a6664870530bd5d04a04362bde597875'
            '8586e10c2a5130e13f5654b809d8d8a6ec43dbd136dce8db022a21a4898f5e00'
            '65ebd695aed37896189e1d55e321bbbceea3f61143c11076cf19178580e374f4'
            '375933e5c3fa227ca46f4d4d7ed5b2ff838c2394d228c062fb23609f202dc1df'
            'cd1ecd581e612b6afc55f1229533529d58833cb3655909ff04aaacc1f21574fd'
            'd6bde633301b8966226796836afad273ae490e07bd44c16809ae39d1515eb9fd'
            'cdf7f169db0a4b7e226648ebecf665d17a7e8fb3ef4f897887936d30e91641f7'
            'a4cddf45dbcf04e87666efd97d83d92c6e4b7987c3587ee907c435613526d4b1'
            '248ba8f1ae8bd910fbd467ac081dbec2918adba0b06985ed3ed684d284fb495a'
            '1ac86a150fdb224277c702860e3b11c9658a1be6e82416c654ecd6b4b1016f82'
            '385ebf1c8c8311737d3d959030e4cfcfcbde180771b5f7e53e5464a30ea1fb9d'
            '789d0fa63933d474af4962cbb86e911f80336dcc89f69eb96b45cb26f6095b1b'
            '5a5f335b63a3757f91f99c8ede9a0aeb5313ad91f34fa13ab091346d5562d1cd'
            '4f204869a65e6ec7b9eb2007de7f769fd7384faf5b666016a62f6ec906854fff')

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
