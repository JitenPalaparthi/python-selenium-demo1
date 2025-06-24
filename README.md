pip install -r requirements.txt
python -m unittest tests/test_text_box.py -v


docker network create jenkins-net

docker volume create jenkins_home

docker run -d \
  --name jenkins \
  --restart unless-stopped \
  --network jenkins-net \
  -p 8080:8080 -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  jenkins/jenkins:lts

  docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword

  d0ff02f5e6c04edbade8b6bba17915c9