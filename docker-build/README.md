# Docker image builder composite action

## What does it do?
This composite action will build a docker image and pushes it to Amazon ECR

## Parameters
* `access-key`: AWS credential
* `secret-access-key`: AWS credential
* `region`: AWS region name
* `ecr-repository`: ECR repository where the image is going to be uploaded to
* `image-name`: name of the docker image to be built (defaults to repository name)
* `image-tag`: tag value for the image (defaults to git commit SHA)

## Example
```yml
    - uses: gha-devops/cicd/build-docker@v1
      id: docker-build
      with:
        access-key: ${{ secrets.AWS_ACCESS_KEY }}
        secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        region: ${{ secrets.AWS_REGION }}
        ecr-repository: ${{ secrets.ECR_REPOSITORY }}
        image-name: ${{ github.repository }}
        image-tag: ${{ github.sha }} 
```

