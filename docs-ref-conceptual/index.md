---
title: Azure CLI 2.0
description: Vue d’ensemble d’Azure CLI 2.0.
author: rloutlaw
ms.author: routlaw
manager: douge
ms.date: 02/27/2017
ms.topic: conceptual
ms.prod: azure
ms.technology: azure-cli
ms.devlang: azure-cli
ms.openlocfilehash: ee82c06e5b5b614b5557c6e6426d2da488468318
ms.sourcegitcommit: 15d6dfaee2075d0abceb2aa2423f0b6ef7b2ac9b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="azure-cli-20"></a>Azure CLI 2.0

Azure CLI 2.0 est la nouvelle expérience de ligne de commande Azure pour la gestion des ressources Azure.
Vous pouvez l’utiliser dans votre navigateur avec [Azure Cloud Shell](/azure/cloud-shell/overview) ou [l’installer](install-azure-cli.md) sur macOS, Linux et Windows et l’exécuter à partir de la ligne de commande.

Azure CLI 2.0 est optimisé pour la gestion et l’administration des ressources Azure à partir de la ligne de commande, et pour la création de scripts d’automatisation qui opèrent sur Azure Resource Manager. Pour créer des machines virtuelles dans Azure avec Azure CLI 2.0, il vous suffit de taper la commande suivante :

```azurecli-interactive
az vm create -n MyLinuxVM -g MyResourceGroup --image UbuntuLTS
```

Utilisez [Cloud Shell](/azure/cloud-shell/overview) pour exécuter l’interface CLI dans votre navigateur ou [l’installer](install-azure-cli.md) sur macOS, Linux ou Windows.
Lisez l’article [Bien démarrer](get-started-with-azure-cli.md) pour commencer à utiliser l’interface de ligne de commande.
Pour plus d’informations sur la version la plus récente, consultez les [notes de publication](release-notes-azure-cli.md).

Les exemples suivants peuvent vous aider à comprendre comment utiliser Azure CLI 2.0 dans certains scénarios courants :
- [Machines virtuelles Linux](/azure/virtual-machines/virtual-machines-linux-cli-samples?toc=%2fcli%2fazure%2ftoc.json&bc=%2fcli%2fazure%2fbreadcrumb%2ftoc.json)
- Interactif : [Créer des machines virtuelles Linux](https://docs.microsoft.com/learn/azure-cli-2-0/index)
- [Machines virtuelles Windows](/azure/virtual-machines/virtual-machines-windows-cli-samples?toc=%2fcli%2fazure%2ftoc.json&bc=%2fcli%2fazure%2fbreadcrumb%2ftoc.json)
- [Web Apps](/azure/app-service-web/app-service-cli-samples?toc=%2fcli%2fazure%2ftoc.json&bc=%2fcli%2fazure%2fbreadcrumb%2ftoc.json)
- [Base de données SQL](/azure/sql-database/sql-database-cli-samples?toc=%2fcli%2fazure%2ftoc.json&bc=%2fcli%2fazure%2fbreadcrumb%2ftoc.json)

Une [référence](/cli/azure/reference-index) détaillée est également disponible. Elle explique comment utiliser chacune des commandes Azure CLI 2.0.

[Bien démarrer avec Azure CLI 2.0](get-started-with-azure-cli.md).


> [!NOTE]
> Si vous utilisez la version précédente de l’interface de ligne de commande (Azure CLI), vous pouvez continuer à l’utiliser.
> Si vous utilisez les deux interfaces de ligne de commande, n’oubliez pas que `azure` est l’ancienne interface CLI (Azure CLI) et que `az` est la nouvelle interface CLI (Azure CLI 2.0).