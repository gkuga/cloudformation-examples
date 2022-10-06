STACK_NAME=dynamodb-example
REGION=ap-northeast-1
TEMPLATE_FILE_PATH=./template.yaml
CAPABILITIES=CAPABILITY_IAM

.PHONY: validate deploy info delete-stack events
validate:
	aws cloudformation validate-template --template-file $(TEMPLATE_FILE_PATH)
deploy:
	aws cloudformation deploy --template-file $(TEMPLATE_FILE_PATH) --stack-name $(STACK_NAME) --region $(REGION) --capabilities $(CAPABILITIES)
info:
	aws cloudformation describe-stacks --stack-name $(STACK_NAME) --region $(REGION)
delete-stack:
	aws cloudformation delete-stack --stack-name $(STACK_NAME) --region $(REGION)
events:
	aws cloudformation describe-stack-events --stack-name $(STACK_NAME) --region $(REGION)

