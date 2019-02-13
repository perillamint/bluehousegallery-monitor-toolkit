# 청와대 청원 게시판 모니터링 툴킷
## 이게 뭔가요
Grafana 와 Prometheus 를 이용, 청와대 청원 게시판을 모니터링하는 툴킷입니다

## 어떻게 쓰나요
이 리포지토리를 클론 받은 뒤, 다음 명령을 실행하세요

```
git submodule update --init --recursive
```

그 다음, `prometheus-bluehousegallery/config.yaml.example` 을 `prometheus-bluehousegallery/config.yaml` 로 복사한 뒤, 내용을 적절히 수정하세요

`docker-compose.yml.example` 을 `docker-compose.yml` 로 복사한 뒤 다음 항목들을 적절히 변경하세요

```
services.grafana.ports[0].published
services.grafana.environment.GF_SECURITY_ADMIN_PASSWORD
```

이 다음

```
sudo docker-compose build
sudo docker-compose up -d
sudo chmod 777 /data/grafana /data/prometheus
```

명령을 이용해 도커 컴포즈로 배포하세요

이후 설정은 [http://docs.grafana.org/] 를 참조하셔서 진행하시면 됩니다
