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
pkgrel=3
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
        '0070-CSMANTLE-perf-ui-browser-avoid-iterating-and-crashin.patch'
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
            '131f332637edade6677a2e2519093a6e07857533d89385c36fd98dcdda85d44d'
            '427144719c26f6f6fd55abe09a889af1c1f8a5bd04fc549d14c06d65c145aeef'
            '6cbee253b282ceb516cb6dca911fddfa2d3465cba24a1919bba68f930e65dba7'
            'ae545dcb9c1fbe7da853b652ed787683829e3fec167c0c2033af1efa4abbea49'
            '26b173da91e5a139300ed126cf7c33401f9135a86a4fdfbc8627303ff9f49680'
            '668d79f3bed8f83eb36ae18e2bef1ab9131295e601551ce7d2ad98e899ea00ec'
            '3e155b47eb442bb50eec7e67458fda2ad6abde2dbb4311c94aac13f05725a144'
            '3c5400e83f3586b2b988bb2cf1e45bb5b0bab9c1dbe1df86323d9bfa4ee30f72'
            '719172b3a937f2728a0c191f5df10667d6df57e3545856c6da92ac18d757de92'
            '514e2e5c2309e995925af6c8964e3a64dc38922ba1fc272c91f2262155b57af1'
            'd1a0cfa7601b35eb130fdfd0aa99e690eba8346e1e212a0942fc2ee5f03f4a5e'
            'c45569a40be3cf8bf189028da8b86b149cca4e881ddd2966b3197319d57ae672'
            '3572be911acafbd7aec6adee2de46005bc58470b76f1b983cb12080590426271'
            '56e74b618b9f98581281df9147654a69ef3679e352b60d210ad13e70db27fc9b'
            '65854223a976ded0a8cfeaf47cd6ae78c0abba0a9dfd1a7e2c2e307af52ba732'
            '1f0fe170d80e9311fb2930df8b9a542c7ed1f993c608c709b0f59ceb09e56cb8'
            'b8ff3fd824299b82b2d0adaf4f9d078f80d57abdd869fad205ea6c8d16c571c5'
            '57631c1862ad752ae190e1bc0650787180af19fcf0d80f94ada02b2ae9e321c4'
            'cdb938bd31ce6060faa4e1474d54cbf20537bbee4fb0fee52cc696d204731773'
            '405ec4dacc53984cf0dd31e064b8922e04a79ba813eacb9643e55d2c961b1d4a'
            '102ff0decc24eae8eebdfe44dda0269b1cd630f60b10494edd2e37f90d5776f1'
            '6649d1320cdf5192b66eecfce2a3348ce9204ed283cd4167507dc83c80388f0c'
            'bc3ecf7c57aea1983c50c250d812cb08207534b0427e4afe3bfe4b8c0f695021'
            'cb120df68639c5c01f05cfea106491fa40e1276d77d0bc7c3d886eb49eb78286'
            'd4e31f167311e349ef8a4d373e0afcfa97434ac5c12ad1f159e2f7f5f7367ac5'
            'aeaea9b8a93676cb4631a5c9ba490abb87551dd75f0b625e51c8bc8a015514d5'
            '2760371620a7df566a158313fca419c8143a66eef13686f1f1a2c309018a201e'
            '46202ed4245219f6aa80ea962ce91cd2dffd92b8e9e9453fb7af0684a6c3070b'
            '6228681ff113f3add1634efea3583b0e1203d4d49cd9b9e64e5c2afbb4d296ce'
            '51c853583384cebb91fda71c22544c10b94dfd74573ae2f0bf3a6785b6db48c2'
            '0f0784ec14648aae4abbb0e02feffa82e7cc23165c55d4c1c44d73061f76f7dd'
            '17735998919aeeb650c188636c01a36c44427fed94148cec3aecf83bb2787041'
            '6892b602fe661758d1d8c80df35aad3fc27fe0eba45a644847e54b2a1dccb5f3'
            'e2cb1d2956e91c3d011da2188c9b9fe879aabe29e9009266e776a1f8cc4d93bf'
            'd5ba79fcaa730835280fc0694d6bc03c8633bdfe9a6199f627895d2ed70be6ee'
            'ed0aa2f3c89cdfbf62bfa6978bab855668e86eb81394b13e081d5c6199a2314a'
            '8512e73cd7ec69bdba440735745b209c0858ea362fd5d5725e141748d400e13c'
            'dcfe03a8789617e5cbeb314e0e64caa9fdcc8f863de96ef3dcb302ee0575e98d'
            '796a6050926d7952826d409e09da3e1b5348bb7c9082fe9a47739f9e3ea37759'
            '80cdf212fb034c87f4ebda7e9196cd9d32ab3a83c9cb9686854a24fb333e7344'
            'b1dc933c13bc47ff0db738b400c60026cd19009d11e040e6dd68f65751ebb143'
            'd0348df39f9036b08a0722038d2e19df5ce931e2a466bc3f3f6bc95a3298067d'
            '581f4ec5645361927338bac300e2360c835cfadc02f4f0c3ef45f11b4384f382'
            '3d783cee60e68bddcb45ad593b388de7bf5d689d638552f382c799430d7dc28a'
            '5a51b285a66d8011b133413e0229eb0142b74b2524b11100a305a4019f7052a5'
            'e9ea1c410b286b38e3331fe70aa1f403b18d1e88cde8af64f6e74858d8d9c435'
            'c876dbf05e71e9ecbf224b6933df227a93d4bce510b1c2950e017f9c88ceb4dc'
            '394c144d7a09b78d37e600ded05f6789259248ab8296a9ddb70ebac913e9b320'
            '6522088d0d4fd11d7a0a527bef1585d372b128ae6a7b81c74208fa94ab2148a8'
            '958e9998315e2407cda0753535a87fd06a81ba9b764def46190163763ea72c1a'
            '2a23f6b9b54406796f334494d3ab5f66253b799a12bcc09e6f523f11c8c53511'
            '75b1cecfcdbb19ef8057ceab2dadafccdf4470a47724ae6b059f05b20caec2cf'
            'f5d48d18330440336d55eaa8fb2bd68b8b680e564ebf181bb86be1cb8c16b664'
            '540c128a7b6272830cb220e19bee76780dacb1a81f54785754e2f6bf1376624c'
            'a8c44d71fdd790602fa5dc1b59c25a16063faa91e3ec779cfd2ebf96b377bb8e'
            '536bed9fa6860e36f0fd69c35c7455be7a7d2a4700638ae4031b0c0103294a28'
            '440bb6a0f74032097e097000084f299a5e1bb7b869558b065f4eb86878aeb477'
            '8bf59be2409f0c6d651b16ff4eb94bb478756f87f735b6170f5849b9c875d01d'
            'c84886760bcbd0811b34701c607295183fd2d658a10dd1aaab61c37ed2a73cf6'
            'a1a4f733c67f72c1af372a690a0ee8d1d765a57ec69c2b270f55e47b4f2efc11'
            '9255af30baadde0d5697527bfa9edc0a7a827e3aaca2f9d41b252c9605b8856e'
            '1055469ccb86c94fa55defdeb077fdec8854e0c5ea65b0e38a7ee4b8b7fbda99'
            'a1ba37bd7b64aca69a6c01530234e61e21cf5f02c31b59282a04d786dc50bb91'
            'c0c3308b9cc026caad535c276ebdc3e15d3f5ec2a4226547250f367cb03f9693'
            '34b338412e5c55f2c46177902bd5b9ad6944aa3d66e297b6d0406c034ba7ea9d'
            '1da992c73211a3f96ada553fb475466d4ba5de06c2fcf72a28f261fb71596fe7'
            '97e617f008a7d9660621a641b37ffb91d9ea915b3494aa6b1007d8d5e3171f67'
            '9a7af8d4140352b0c255c492dfc5c299ca363adef06108c90067215a751d1bd3'
            '89aa49a6a91db1980e3419c5069bd81e0e2ed2e59e3ffbc3ca88168b666d9f3e'
            'edd804e0c79f1ed654f6da15a9afd8db70b4f3679075b012905f3f14ae44578b')

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
