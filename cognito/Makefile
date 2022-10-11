STACK_NAME=userpool
REGION=ap-northeast-1
TEMPLATE_FILE_PATH=./template.yaml
CAPABILITIES=CAPABILITY_IAM

.PHONY: deploy info delete-stack events
deploy:
	aws cloudformation deploy --template-file $(TEMPLATE_FILE_PATH) --stack-name $(STACK_NAME) --region $(REGION) --capabilities $(CAPABILITIES)
info:
	aws cloudformation describe-stacks --stack-name $(STACK_NAME) --region $(REGION)
delete-stack:
	aws cloudformation delete-stack --stack-name $(STACK_NAME) --region $(REGION)
events:
	aws cloudformation describe-stack-events --stack-name $(STACK_NAME) --region $(REGION)
