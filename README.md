# Vmware-issue--solved
Issue installing vmware with all modules

Follow the steps to solved this issue. This is what helped me.

cd /usr/lib/vmware/modules/source
git clone https://github.com/mkubecek/vmware-host-modules
cd vmware-host-modules
git checkout workstation-16.2.3
make
tar -cf vmnet.tar vmnet-only
tar -cf vmmon.tar vmmon-only
mv vmnet.tar /usr/lib/vmware/modules/source/
mv vmmon.tar /usr/lib/vmware/modules/source/
vmware-modconfig --console --install-all
