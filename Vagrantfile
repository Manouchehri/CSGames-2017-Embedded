Vagrant.configure("2") do |config|
	config.vm.box = "bento/ubuntu-16.04"

	config.vm.provision "shell", inline: "modprobe binfmt_misc", privileged: true

	config.vm.provision "docker" do |d|
		d.pull_images "fkrull/qemu-user-static"
		d.run "fkrull/qemu-user-static",
			args: "--rm --privileged",
			cmd: "enable",
			restart: "no"
	end
end
