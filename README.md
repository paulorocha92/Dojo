# Dojo


3. Show cost estimate breakdown​
Infracost parses the project locally to determine resource types and quantities needed to calculate costs. The --path flag can point to a Terraform directory or plan JSON file.

cd my-terraform-project
infracost breakdown --path .

4. Show cost estimate diff​
Generate an Infracost JSON file as the baseline:

infracost breakdown --path . --format json --out-file infracost-base.json

Edit your Terraform project. If you're using our example project, try changing the instance type:
vim main.tf

Generate a diff by comparing the latest code change with the baseline:
infracost diff --path . --compare-to infracost-base.json