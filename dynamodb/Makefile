STACK_NAME=dynamodb-example
CHANGE_SET_NAME=dynamodb-example
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
create-change-set:
	aws cloudformation create-change-set --change-set-name $(CHANGE_SET_NAME) --template-body file://$(PWD)/$(TEMPLATE_FILE_PATH) --stack-name $(STACK_NAME) --region $(REGION) --capabilities $(CAPABILITIES)
list-change-sets:
	aws cloudformation list-change-sets --stack-name $(STACK_NAME)
describe-change-set:
	aws cloudformation describe-change-set --stack-name $(STACK_NAME) --change-set-name $(CHANGE_SET_NAME)
execute-change-set:
	aws cloudformation execute-change-set --stack-name $(STACK_NAME) --change-set-name $(CHANGE_SET_NAME)
delete-change-set:
	aws cloudformation delete-change-set --stack-name $(STACK_NAME) --change-set-name $(CHANGE_SET_NAME)

