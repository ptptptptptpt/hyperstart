all-local: initrd

if WITH_VBOX
initrd-local:
	bash ./make-initrd.sh vbox
else
initrd-local:
	bash ./make-initrd.sh
endif

cbfs-local:
	bash ./make-initrd.sh cbfs

kernel-local:
	hyperctl build -t hyperstart-dev:latest .
	hyperctl run --rm hyperstart-dev:latest cat /root/build/result/kernel >kernel.new && mv -f kernel.new kernel
	hyperctl run --rm hyperstart-dev:latest cat /root/build/result/modules.tar >modules.tar
