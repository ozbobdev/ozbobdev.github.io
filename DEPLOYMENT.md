# Azure Storage Deployment Instructions

This website is designed to be deployed to Azure Storage static website hosting.

## Files Structure
```
/
├── index.html          # Main HTML file
├── style.css           # Stylesheet
└── img/
    └── bg.jpg          # Background image
```

## Deployment to Azure Storage $web folder

To deploy this website to Azure Storage:

1. Create an Azure Storage account (if not already created)
2. Enable static website hosting on the storage account
3. Upload all files to the `$web` container:
   - index.html (root)
   - style.css (root)
   - img/bg.jpg (img folder)

### Using Azure CLI
```bash
# Upload files to $web container
az storage blob upload-batch -s . -d '$web' --account-name <storage-account-name>
```

### Using Azure Portal
1. Navigate to your Storage Account
2. Go to "Static website" under "Settings"
3. Enable static website hosting
4. Note the primary endpoint URL
5. Go to "Containers" and select "$web"
6. Upload all files maintaining the directory structure

The website will be accessible at your Azure Storage static website endpoint.
