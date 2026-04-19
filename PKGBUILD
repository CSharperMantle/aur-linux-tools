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
pkgver=6.19.13
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
        '0001-add-sysctl-to-allow-disabling-unprivileged-CLONE_NEW.patch'
        '0002-udmabuf-Do-not-create-malformed-scatterlists.patch'
        '0003-Arch-Linux-kernel-v6.19.13-arch0.patch'
        '0004-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
        '0005-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
        '0006-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
        '0007-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
        '0008-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
        '0009-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
        '0010-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
        '0011-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
        '0012-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
        '0013-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
        '0014-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
        '0015-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
        '0016-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
        '0017-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
        '0018-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
        '0019-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
        '0020-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
        '0021-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
        '0022-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
        '0023-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
        '0024-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
        '0025-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
        '0026-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
        '0027-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
        '0028-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
        '0029-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
        '0030-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
        '0031-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
        '0032-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
        '0033-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
        '0034-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
        '0035-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
        '0036-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
        '0037-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
        '0038-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
        '0039-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
        '0040-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
        '0041-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
        '0042-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
        '0043-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
        '0044-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
        '0045-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
        '0046-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
        '0047-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
        '0048-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
        '0049-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
        '0050-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
        '0051-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
        '0052-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
        '0053-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
        '0054-AOSCOS-loongarch-fix-DMA-address-offset.patch'
        '0055-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
        '0056-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
        '0057-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
        '0058-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
        '0059-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
        '0060-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
        '0061-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
        '0062-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
        '0063-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
        '0064-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
        '0065-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
        '0066-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
        '0067-BORE-linux6.19.7-bore-6.6.2.patch'
        '0068-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
        '0069-BACKPORT-FROMLIST-perf-annotate-Use-jump__delete-whe.patch'
)
validpgpkeys=(
  'ABAF11C65A2970B130ABE3C479BE3E4300411886'  # Linus Torvalds
  '647F28654894E3BD457199BE38DBBDC86092693E'  # Greg Kroah-Hartman
)
sha256sums=('0559b1fea740e71714b4368023902b7d098c45ac1faa3176eab392c867645648'
            'SKIP'
            '2e187734d8aec58a3046d79883510d779aa93fb3ab20bd3132c1a607ebe5498f'
            'b1315cb77a35454e1af9172f821a52e2a0cb18561be05a340d21cf337b01ae61'
            '2d5e2f8d40b6f19bf2e1dead57ca105d72098fb0b418c09ff2e0cb91089710af'
            '97e3c2081843327c9b646e89ced9cf63f018d5118d95c951bf7e004ab45cc3b3'
            '28c3145f29c940832d877c150a12175e39d4d51d0f3c55d0b1e617a0386f6783'
            '9f162f6dae38fee0697d12b84eaab83e53906c7bdda4e03ac7212687238db213'
            'd6e0a7e40c3094939c90d6bd85e40bd76c994b3f911957dbfba2da47c1a23942'
            'b2f2af2730be0bda95c8b7de556b4b340105d291d8d6b37bc9abed336629120e'
            'a839d4a4c44e1b14cfd6631453cb96a28bcd4210d61ab264c61813b56ee1969f'
            '26f133d0a9ec7f3010ba3bdbbef0fd5fa1b758df63bd515d9f0971d1572b8994'
            '28858f1b1b5f800667833d94c629b15ddf87c1327c38aaea095a3c0125a7689d'
            'be4b00d40eb968e6dcb4f44f89d59cef5bbdd13a08d39d39ca961f63b25d1466'
            '305baadd9b7653c9764285252acbbba31fee18ba7d1f05364190b085f0180b6e'
            'b12e28359043be63c3c644ae0e346e8a6a36ec8e51e812ec4f028a633bae3e18'
            'ebd4de4b275bea5e9297c784b59a2ff22b4b7422bf885a2a37cf2c3e45813bed'
            'f32a14bc41555c6d0b87fba2a7f1288f5cc6d313613e7ede88a3ab47e5c156e1'
            'ca13c050738e79bba2bf9a55aada7b1dd3f493c0bdf903af21c541b9c0139b22'
            'ba175a02ee5192f3d1054ae73475ae9d0bbdd8d23cad26f71abc7571be403689'
            '7c2e3748f97d2af1e84f0dd4bbcb22de812ff9a98bb3e94b030388a5e08acac1'
            'da955abb3ecedda6230f078cab189aae5515629a05f41b8f4393f50c72d1fcc4'
            '1625079009519f1a7f326d969fffe4e1f723ef4f84e1e38ac69af7742c73aae7'
            '9289008bd46076a992a929e4fa5b88366115acee15a79f14446779833dd05ba9'
            'd96e7a15b041d6744563514cbf1fae656386049e145083e299daf3ed59779013'
            '8d253b8816862b4301c5f28ccc7623a7e7a78a268c5eec277298ddd9349b2ccb'
            '5abdb0841f7c7f6d4b729935e61676a828c5b6c17c02b760bf15dcc80bb179ea'
            'ddceed6348877176f38e8ee5fb47ffe4c4f8554989f746a94e1420a8473c9bd3'
            '45f04fce79b27d2cab5c8d65a51f417bb97c0f8be64543742c9d1c09fe7346a5'
            'c0212c86f707bc81346e02d188f35b133c872a074817109da57ff9bc5dda1723'
            '92f5d5a159f9defdee16a31bf39f5efa836070d340f77c0f7839b69e140ac797'
            'dcb6ecca1ee23bc4060d3e4c12c175aae19a7bdc2d461944d55ec235c033d44b'
            'e82a0732f6ed737644facf78a7fc068975d577bdcfcd733fb65c5b84243ff364'
            '10cda2b725c434a15292ffab63889ca5f66ac1beb9ac3119663df59f56dc6c70'
            '103b04a59445ad5f86cf25df9ac93bde7ca5c8b02c7e8ae346cecef4e6daf91a'
            '68328fc993be3bfe24decfee86624ae954d72600b7a4943c6f9f6ef91f3f39b2'
            'ed43ad3bca54ba818903fb8d086a659bcc763cf9a8d555439a63e2652607ef87'
            '7376d1d61fb215bde8a967d80310496919d604831234ab23836d28a3c08a57e7'
            'dec2f498e4e11c56ffe03e8b14512c9a1d7667f399c906ca989d9fa200ccffad'
            '352dc685c1e4b948077d7c0b1d4f86ed308a74f11ace2e0c5bdfe210fde6f0c0'
            'dbd35aef2543c2222169f17e81941636ee874158c61d37e18329000400e84490'
            'f898a578a1b9898ba3389dc85fa43326d69a5c4cecb93fc5b713c53482da51e1'
            'ba7b63bc17f997d5fae4703412bb3dab201fe3adc71d33a84ee3e75d56af03e7'
            '1228e041726f1405ae7ba2b775613f928063df4e4362498768318aecd504552f'
            '13ff0ea453cd9e6daa1fdf4bedb0d10b1a63f3d68d7a2e994a37a0dfb9f027ec'
            '19af1d0171682b051cc47fb8f2ac223b7cd48b9295b3c2201e4a2f9b5a2ad357'
            'f2863c701659dfd51ef01e165146802652158067712323c5be3d0fe94eba0ca2'
            '290dd23043dfe0d693590d8a24f4348d0359b0ba9fe55f86c1c9bdd394836c13'
            '333834bb6b71c1414fc0c06ca112646915a73c1e33389507f72f17f4be2b6f83'
            'c702a7b76ba84e8f3d6aca3c5194478af6aa440df7014b7026689991c2fc04f2'
            'eb28e64a6761b578a8d88e0c58588241c050cdfbdd2704dfb55dfda94aff1441'
            '252cad13b42d923d3de72506e53b0a1c2cbb43be392eea51fbaf4c39924c7c87'
            'bd9ab444aff2efe45d8d9c81f9b70be70983a4d5561ed7b0d4018859e4c4785c'
            '8b3f6d1b5c906381a9544bf0f0c2d927dab5d2cc1bec20d17ec75dfaf7f92c18'
            'c1c9eb7aafa4d110face1b7fbd9d7ad8738314921e2ac8b4bfd401d1f3988b3d'
            'eb4164cf214406c2f3d4cecb5beefeaa2053a1af2f65112e641857933a23df00'
            'd2587ae6fbff902ad28c5b77c713a6dd1e3e1ab6bde45a02942a05dfa00c4d9d'
            'cacb3076dac58b448752c9b6407e09d03ea9a7dfe88bb5cd948b562e446fcd72'
            '9282284074042410b6ae271f7a81a97a47818658727edcc9e79cbe6f4fe08c53'
            '7083968121c0be15c6c730a868b35d17ef2182d7658c1b7fedf85bc3c9ec3d52'
            'f6fda9a5f27293e944de8981f6ab3b5594f35b02a377631572115f2d5eefb447'
            '4ab6180532c4cfb0677324d0301b06dcbd82700738981b9642b28bf051f46105'
            'f51292008be5a4055f81d1fce9af820648c15b75133610c50a83c7c2914d15d1'
            'e7ef8e20d4d5e6da2826ba081788d6f616eda1ad62d5e361ce7b115e3a1e8a95'
            'b54c8eabb5f5b75a0e386355c9ba03d75e6629e1162d47751c89700edfd31530'
            'f8b9bc983a10402cd61271506707f0b82950cc5477fbb0fe7fd77fc9815a1ab5'
            'b215ebb6341a092dbd03760e7cc78e2bd2e6c293f42df34b63b77c5a998fc8fe'
            '3fe8ed5f7c2e4597483c2c321ceb68eeb02f5f8926393e8631a94d3f31948679'
            '13aacc150ca4c72a5e5048cd484310e39b5da97b93cb5d9a1f6e1d6c061a9c46'
            '253544d2eef0a4793f86f41c2bde7b8d6f84d6e0820d2c25751b3485ae8dcc86'
            '5ebaf2179ffb816fbdd0e6b821a3b339b2b39d847fb089069d367cfe0ce4f436'
            'c457ea22993752a0189731c1b3fa4639178a760b1b773830fc5bae631a0a8b84'
            'c57f150c5cb7e5c77299b016ba5d4d2ff7dfa79e03782a0debc1960a6e7b9cd1'
            'b33992f9fd6c64ab0133ff37da6c565a6da0f257b4e5fe0705cf2a49f1139d7a')

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
