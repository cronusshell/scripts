# scripts

Esse script vai facilitar a instalação do Zsh, Oh! my Zsh, como tambem os temas e fontes necessarios para rodar o zsh perfeitamente sem os erro graficos no terminal, como o tema POWER LEVEL 9K, necessecita de temas do Power Level.

no Script passará por atualizações, mas até o presente momento ele está programado para rodar no Debian e derivados, se você não usa os mesmo, suguiro que você faça as alterações no codigo fonte, para de acordo com o seu sistema.

__________________________________________________________________________________________________________________________

##select nome in "${opcoes[@]}"
do
        case $nome in
                "dependencias")
                sudo apt-get install git -y && sudo apt-get install wget -y  <<<<---- Alterações deve ser feita aqui.
                ;;
                "zsh")
                sudo apt-get install zsh <<<<<---- Aqui tambem.
                ;;
                "oh-my-zsh")
                sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
                ;;
                "powerFonts")
                git clone https://github.com/powerline/fonts.git --depth=1 && cd fonts && sudo chmod +x install.sh && ./install.sh && cd .. && sudo rm -rf fonts
                ;;
                "powerlevel9k")
                git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
                ;;
                "sair")
                break
                ;;
                *)echo "opção invalida";;
                
                --------------------------------------------------------------------------------------------
                
                
                OBS:: Em alguns sistemas o prefixo -y não é aceito, tambem aconselho que retire ele... o prefixo serve para pular a parte da permissão de instalação, que geralmente o sistema pergunta; seria uma resposta prévia.
                
                
