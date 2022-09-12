kubectl config set-context --current --namespace=rabbitmq-system
kubectl port-forward "service/hello-world" 15672

username="$(kubectl get secret hello-world-default-user -o jsonpath='{.data.username}' | base64 --decode)"
echo "username: $username"
password="$(kubectl get secret hello-world-default-user -o jsonpath='{.data.password}' | base64 --decode)"
echo "password: $password"
username: default_user_qjd8kZ9ClxXI5LQu2lf
password: K4PlSa2TIhwOB8HbCx0zBWb_suDV1TLa
