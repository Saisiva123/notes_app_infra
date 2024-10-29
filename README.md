#### Infrastructure required for deploying a NOTES application:

1. Need to have a VPC covering 2 AZ's.
2. Need to have 2 public subnets and 2 private subnets.
3. Need to have a ECS cluster where frontend tasks run on public subnet and backend tasks run on private subnet.
- Need to setup a service discovery for task communication.

4. Need to setup security groups at the service level.
5. Need to setup internet facing Loadbalancer in the public subnet and the internal private load balancer in the private subnet.
6. Need to setup a NAT gateway inside the public subnet and should able to attach it to the private subnet through route tables.

#### Manual setup

1. Need to create a DNS record pointing to the internet facing load balacner which is in the private subnet.

#### FLow and steps of Deployment:

1. Triggering the Github Workflow for creating the infrastructure.
2. Manually trigger the CI/CD pipeline for the backend server while maintaining different environments like staging and production.
3. Manually trigger the CI/CD pipeline for the frontend server while maintaining different environments like staging and production. 