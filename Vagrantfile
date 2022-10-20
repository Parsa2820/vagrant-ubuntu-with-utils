Vagrant.configure("2") do |config|
    # base box
    config.vm.box = "ubuntu/jammy64"
    config.vm.hostname = "ubuntu-with-utils"

    # hardware resources
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
        vb.cpus = 2
    end

    # install docker
    config.vm.provision "docker" do |d|
        d.pull_images "busybox"
    end
    
    # install utilities
    config.vm.provision "shell", inline: <<-SCRIPT
        apt-get update
        apt-get upgrade -y
        apt-get install -y \
            bash-completion \
            curl \
            git \
            htop \
            jq \
            net-tools \
            nmap \
            python3 \
            python3-pip \
            python3-venv \
            telnet \
            tmux \
            tree \
            vim \
            wget
    SCRIPT
end