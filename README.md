# Help for DevOps



## Getting started

Decisions Log
    API Gataway to use (Kong, Traefik , Nginx and Haproxy)


Installation manuals
    
    ```
    kubectl create namespace argocd
    argocd app create kong-api-gateway --repo https://github.com/Kong/charts.git --path charts/kong/ --dest-server https://kubernetes.default.svc --dest-namespace kong


    kubectl create namespace traefik
    argocd app create traefik-api-gateway --repo https://github.com/traefik/traefik-helm-chart.git --path traefik/ --dest-server https://kubernetes.default.svc --dest-namespace traefik

    ```



## Add your files

- [ ] [Create](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#create-a-file) or [upload](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#upload-a-file) files
- [ ] [Add files using the command line](https://docs.gitlab.com/ee/gitlab-basics/add-file.html#add-a-file-using-the-command-line) or push an existing Git repository with the following command:


