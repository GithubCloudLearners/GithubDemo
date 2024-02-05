export GH_USERNAME='AndresMPaws'

export GH_TOKEN='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'

export GH_IMAGE_NAME='hello-world'

export GH_TAGNAME='ghcr.io/andresmpaws/$GH_IMAGE_NAME:$GH_VER'

export GH_VER='1.0.0'

echo $GH_TOKEN | docker login ghcr.io -u $GH_USERNAME --password-stdin

docker tag $GH_IMAGE_NAME:latest $GH_TAGNAME

docker push $GH_TAGNAME