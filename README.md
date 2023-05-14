# Js7_bgfi
Repository to store script of JS7
https://qiita.com/saitamanokusa/items/ffb8f05cbc8e75d435ce#%E5%8F%82%E8%80%83-docker-composeyml-ver-251%E3%81%BE%E3%81%A7
create following folders in working directory

mkdir db_data
mkdir js7-agent-primary
mkdir js7-controller-primary
mkdir js7-joc-primary-config
mkdir js7-joc-primary-logs

.
├── .env
├── db_data
├── docker-compose.yml
├── hibernate.cfg.xml
├── js7-agent-primary
├── js7-controller-primary
├── js7-joc-primary-config
└── js7-joc-primary-logs

docker-compose -f  docker-compose.yml up -d
cp -f hibernate.cfg.xml js7-joc-primary-config/
docker compose exec js7-joc-primary /bin/sh -c /opt/sos-berlin.com/js7/joc/install/joc_install_tables.sh
docker compose restart js7-joc-primary
