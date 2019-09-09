# Assignment1
Week 2
cd ~
  /bin/bash
  perl -MNet::FTP -e \
    '$ftp = new Net::FTP("ftp.ncbi.nlm.nih.gov", Passive => 1);
     $ftp->login; $ftp->binary;
     $ftp->get("/entrez/entrezdirect/edirect.tar.gz");'
  gunzip -c edirect.tar.gz | tar xf -
  rm edirect.tar.gz
  builtin exit
  export PATH=${PATH}:$HOME/edirect >& /dev/null || setenv PATH "${PATH}:$HOME/edirect"
  ./edirect/setup.sh
  echo "export PATH=\${PATH}:/home/xiyuliu/edirect" >> $HOME/.bashrc
cat .bashrc
esearch -db pubmed -query "tumor mutation burden Pediatric" |   efetch -format abstract
esearch -db pubmed -query "tumor mutation burden Pediatric" |   efetch -format abstract > pubmed.090421.v1.txt
ls
head pubmed.090421.v1.txt
vi pubmed.090421.v1.txt
:%s/\n//g    (#remove all of the line enters by searching for \n and replacing with nothing)
:wq
head pubmed.090421.v1.txt
pip install wordcloud
ls -l
pip install wordcloud --user
wordcloud_cli --text pubmed.090421.v1.txt --imagefile wordcloud.png
ls -l
(#open a new window connected to the server)
rsync -avz xiyuliu@trgn.usc.edu:~/wordcloud.png ~/Desktop
enter xiyuliu@trgn.usc.edu's password
receiving file "wordcloud.png"
esearch -db pubmed -query "prediction protein subcellular localization" |   efetch -format abstract
esearch -db pubmed -query "prediction protein subcellular localization" |   efetch -format abstract > pubmed.090422.v1.txt
ls
head pubmed.090422.v1.txt
vi pubmed.090422.v1.txt
:%s/\n//g    (#remove all of the line enters by searching for \n and replacing with nothing)
:wq
head pubmed.090422.v1.txt
pip install wordcloud
ls -l
pip install wordcloud --user
wordcloud_cli --text pubmed.090422.v1.txt --imagefile wordcloud.png
ls -l
(#open a new window connected to the server)
rsync -avz xiyuliu@trgn.usc.edu:~/wordcloud.png .
enter xiyuliu@trgn.usc.edu's password
receiving file "wordcloud.png"
