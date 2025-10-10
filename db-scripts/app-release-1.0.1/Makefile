# Configuration using jenkins environment variables - updated sql folderfile names
DB_SERVER ?= localhost
ENVIRONMENT ?= dev
DB_NAME ?= bstdb
DB_USER ?= bstdev
DB_PASSWORD ?= $(if $(DB_PASSWORD),$(DB_PASSWORD),$(error DB_PASSWORD is not set))
SQLCMD=sqlcmd -S $(DB_SERVER) -U $(DB_USER) -P $(DB_PASSWORD) -C -b -r1

# Default target
all: post-deploy

# Run post-deployment scripts
post-deploy:
	@echo ">>> Waiting 180 seconds before starting deployment..."
	@sleep 180
	@echo "Running post-deploy scripts..."
	@$(SQLCMD) -d $(DB_NAME) -i create_dummy_table.sql
	@$(SQLCMD) -d $(DB_NAME) -i insert_data_dummy_table.sql	
	@echo "DB-deploy scripts completed."

# Help
help:
	@echo "  make post-deploy   - Run deploy SQL scripts"
