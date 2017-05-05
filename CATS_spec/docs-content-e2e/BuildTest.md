# Build Test

## Checked Lists
A new style is now available for bulleted lists. You can render lists with check marks. Here's an example:

> [!div class="checklist"]
> * Log in to Azure
> * Create a resource group
> * Prepare the configuration
> * Create a virtual machine
> * Configure the firewall
> * Snapshot the virtual machine
> * Run management tasks

To render the above list, you would write the following Markdown:

```markdown-interavtive
> [!div class="checklist"]
> * Log in to Azure
> * Create a resource group
> * Prepare the configuration
> * Create a virtual machine
> * Configure the firewall
> * Snapshot the virtual machine
> * Run management tasks
```

## Next Steps
We're rolling out a new Markdown extension targeted at providing a consistent way for writers to show "next steps" at the end of their articles. Here's an example:

> [!NEXT]
> Next step content, [sometimes blue](http://docs.microsoft.com), sometimes not.
> Lorem ipsum dolor sit amet, [consectetur adipisicing elit](http://docs.microsoft.com).

To render the above block, you would write the following Markdown:

```markdown-interavtive
> [!NEXT]
> Next step content, [sometimes blue](http://docs.microsoft.com), sometimes not.
> Lorem ipsum dolor sit amet, [consectetur adipisicing elit](http://docs.microsoft.com).
```

## Azure Cli Code sample

When the feature is live on review, the following should display the enhanced code block:

```azurecli-interactive
az group create --name myResourceGroup --location westeurope
``` 