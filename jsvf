#/bin/bash
dir=$(echo "/home/$USER/")
if [ -e ~/.jsvf.last ]
then
        nrm=$(cat .jsvf.last |sed -n 1p)
        tome=$(cat .jsvf.last |sed -n 2p)
        chapter=$(cat .jsvf.last |sed -n 3p)
fi
if [ $(pwd) != "$dir" ]
then
        cd "$dir"
fi
printf "\033c"
ls . |grep -v list.txt > list.txt
cat -n list.txt
read -p "Tapez le numéro du manga [$nrm] : " nrm
read -p "Tapez le numéro du tome [$tome] : " tome
manga=$(cat list.txt |sed -n $nrm'p')
read -p "Tapez le numéro du chapitre [$chapter] : " chapter
page=$(wget -q -O - http://funquizzes.fun//uploads/manga/"$manga"/$chapter/ |awk '{print $3}' |grep -E .jpg |sed '$!d' |tr '>' ' ' |awk '{print $2}' |tr -d [:alpha:] |tr -d [:punct:])
echo "$nrm" > ~/.jsvf.last
echo "$tome" >> ~/.jsvf.last
echo "$chapter" >> ~/.jsvf.last
printf "\033c"
echo -e "Téléchargement en cours de \e[31m$manga\e[0m, tome \e[31m$tome\e[0m, chapitre \e[31m$chapter\e[0m\e[0m\n"
for i in $( eval echo {1..0$page} )
do
        wget -q http://funquizzes.fun//uploads/manga/"$manga"/$chapter/$i.jpg -P "$manga"/"Tome $tome"/"Chapitre $chapter"/
        if [ -e "$manga"/"Tome $tome"/"Chapitre $chapter"/"$i.jpg" ]
        then
                echo -e  "•\033[32m Page \e[31m$i\e[0m enregistrée ! \033[0m"
        else
                wget -q http://funquizzes.fun//uploads/manga/"$manga"/$chapter/${i:1}.jpg -P "$manga"/"Tome $tome"/"Chapitre $chapter"/
                if [ -e "$manga"/"Tome $tome"/"Chapitre $chapter"/"${i:1}.jpg" ]
                then
                        echo -e  "\033[32m -> Page \e[31m${i:1}\e[0m enregistrée ! \033[0m"
                else
                        echo -e  "\033[31m -> Erreur, page \e[31m${i:1}\e[0m non enregistrée ! \033[0m"
                fi
        fi
done
