---
title: "Options de configuration d’Azure CLI"
description: Comment configurer Azure CLI 2.0
keywords: "Azure CLI, configuration, paramètres, Azure"
author: sptramer
ms.author: sttramer
manager: routlaw
ms.date: 12/13/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: azurecli
ms.service: multiple
ms.openlocfilehash: d60ede5b971ee2489482fb5a72bde9bf5389d37c
ms.sourcegitcommit: 8606f36963e8daa6448d637393d1e4ef2c9859a0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="azure-cli-20-configuration"></a><span data-ttu-id="293a9-104">Configuration d’Azure CLI 2.0</span><span class="sxs-lookup"><span data-stu-id="293a9-104">Azure CLI 2.0 configuration</span></span>

<span data-ttu-id="293a9-105">Azure CLI 2.0 permet à la configuration utilisateur de remplacer les paramètres internes, comme la journalisation et la collecte de données et de fournir des options par défaut pour certains paramètres requis.</span><span class="sxs-lookup"><span data-stu-id="293a9-105">The Azure CLI 2.0 allows for user configuration to override internal settings such as logging and data collection, and provide default options for some required parameters.</span></span> <span data-ttu-id="293a9-106">L’interface CLI permet de gérer facilement certaines de ces valeurs grâce à la commande `az configure`, et d’autres valeurs peuvent être définies dans un fichier de configuration ou avec des variables d’environnement.</span><span class="sxs-lookup"><span data-stu-id="293a9-106">The CLI offers a convenience command for managing some of these values, `az configure`, and other values can be set in a configuration file or with environment variables.</span></span>

<span data-ttu-id="293a9-107">Les valeurs de configuration utilisées par l’interface CLI sont évaluées dans l’ordre suivant. Les éléments situés en haut de la liste sont prioritaires.</span><span class="sxs-lookup"><span data-stu-id="293a9-107">Configuration values used by the CLI are evaluted in the following precedence, with items higher on the list taking priority.</span></span>

1. <span data-ttu-id="293a9-108">Paramètres de ligne de commande</span><span class="sxs-lookup"><span data-stu-id="293a9-108">Command-line parameters</span></span>
2. <span data-ttu-id="293a9-109">Variables d’environnement</span><span class="sxs-lookup"><span data-stu-id="293a9-109">Environment variables</span></span>
3. <span data-ttu-id="293a9-110">Valeurs du fichier de configuration ou définies avec `az configure`</span><span class="sxs-lookup"><span data-stu-id="293a9-110">Values in the configuration file or set with `az configure`</span></span>

## <a name="cli-configuration-with-az-configure"></a><span data-ttu-id="293a9-111">Configuration de l’interface CLI avec az configure</span><span class="sxs-lookup"><span data-stu-id="293a9-111">CLI configuration with az configure</span></span>

<span data-ttu-id="293a9-112">La commande [az configure](/cli/azure/?view=azure-cli-latest#az_configure) permet de définir les valeurs par défaut de l’interface CLI.</span><span class="sxs-lookup"><span data-stu-id="293a9-112">You set defaults for the CLI with the [az configure](/cli/azure/?view=azure-cli-latest#az_configure) command.</span></span>
<span data-ttu-id="293a9-113">Cette commande accepte un seul argument, `--defaults`, qui est une liste séparée par des espaces de paires `key=value`.</span><span class="sxs-lookup"><span data-stu-id="293a9-113">This command takes one argument, `--defaults`, which is a space-separated list of `key=value` pairs.</span></span> <span data-ttu-id="293a9-114">Les valeurs fournies sont utilisées par l’interface CLI à la place des arguments requis.</span><span class="sxs-lookup"><span data-stu-id="293a9-114">The provded values are used by the CLI in place of required arguments.</span></span>

<span data-ttu-id="293a9-115">Voici une liste des touches disponibles que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="293a9-115">The following is a list of available keys that you can use.</span></span>

| <span data-ttu-id="293a9-116">NOM</span><span class="sxs-lookup"><span data-stu-id="293a9-116">Name</span></span> | <span data-ttu-id="293a9-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="293a9-117">Description</span></span> |
|------|-------------|
| <span data-ttu-id="293a9-118">group</span><span class="sxs-lookup"><span data-stu-id="293a9-118">group</span></span> | <span data-ttu-id="293a9-119">Groupe de ressources par défaut à utiliser pour toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="293a9-119">The default resource group to use for all commands.</span></span> |
| <span data-ttu-id="293a9-120">location</span><span class="sxs-lookup"><span data-stu-id="293a9-120">location</span></span> | <span data-ttu-id="293a9-121">Emplacement par défaut à utiliser pour toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="293a9-121">The default location to use for all commands.</span></span> |
| <span data-ttu-id="293a9-122">web</span><span class="sxs-lookup"><span data-stu-id="293a9-122">web</span></span> | <span data-ttu-id="293a9-123">Application par défaut à utiliser pour toutes les commandes `az webapp`.</span><span class="sxs-lookup"><span data-stu-id="293a9-123">The default app name to use for `az webapp` commands.</span></span> |
| <span data-ttu-id="293a9-124">vm</span><span class="sxs-lookup"><span data-stu-id="293a9-124">vm</span></span> | <span data-ttu-id="293a9-125">Nom de la machine virtuelle par défaut à utiliser pour les commandes `az vm`.</span><span class="sxs-lookup"><span data-stu-id="293a9-125">The default VM name to use for `az vm` commands.</span></span> |
| <span data-ttu-id="293a9-126">vmss</span><span class="sxs-lookup"><span data-stu-id="293a9-126">vmss</span></span> | <span data-ttu-id="293a9-127">Nom VMSS par défaut à utiliser pour les commandes `az vmss`.</span><span class="sxs-lookup"><span data-stu-id="293a9-127">The default VMSS name to use for  `az vmss` commands.</span></span> |
| <span data-ttu-id="293a9-128">acr</span><span class="sxs-lookup"><span data-stu-id="293a9-128">acr</span></span> | <span data-ttu-id="293a9-129">Nom du Registre du conteneur par défaut à utiliser pour les commandes `az acr`.</span><span class="sxs-lookup"><span data-stu-id="293a9-129">The default container registry name to use for `az acr` commands.</span></span> |
| <span data-ttu-id="293a9-130">acs</span><span class="sxs-lookup"><span data-stu-id="293a9-130">acs</span></span> | <span data-ttu-id="293a9-131">Nom du service du conteneur par défaut à utiliser pour les commandes `az acs`.</span><span class="sxs-lookup"><span data-stu-id="293a9-131">The default container service name to use for `az acs` commands.</span></span> |

<span data-ttu-id="293a9-132">Par exemple, voici comment vous devez définir le groupe de ressources et l’emplacement par défaut pour toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="293a9-132">As an example, here's how you would set the default resource group and location for all commands.</span></span>

```azurecli
az configure --defaults "location=westus2 group=MyResourceGroup"
```

## <a name="cli-configuration-file"></a><span data-ttu-id="293a9-133">Fichier de configuration de l’interface CLI</span><span class="sxs-lookup"><span data-stu-id="293a9-133">CLI configuration file</span></span>

<span data-ttu-id="293a9-134">Le fichier de configuration de l’interface CLI contient d’autres paramètres utilisés pour gérer le comportement de l’interface CLI.</span><span class="sxs-lookup"><span data-stu-id="293a9-134">The CLI configuration file contains other settings that are used for managing CLI behavior.</span></span> <span data-ttu-id="293a9-135">Le fichier de configuration se trouve sous `$AZURE_CONFIG_DIR/config`.</span><span class="sxs-lookup"><span data-stu-id="293a9-135">The configuration file itself is located at `$AZURE_CONFIG_DIR/config`.</span></span> <span data-ttu-id="293a9-136">La valeur par défaut `AZURE_CONFIG_DIR` est `$HOME/.azure/config` sur Linux et macOS, et `%USERPROFILE%\.azure\config` sous Windows.</span><span class="sxs-lookup"><span data-stu-id="293a9-136">The default value of `AZURE_CONFIG_DIR` is `$HOME/.azure/config` on Linux and macOS, and `%USERPROFILE%\.azure\config` on Windows.</span></span>

<span data-ttu-id="293a9-137">Les fichiers de configuration sont écrits sous le format de fichier INI.</span><span class="sxs-lookup"><span data-stu-id="293a9-137">Configuration files are written in the INI file format.</span></span> <span data-ttu-id="293a9-138">Ces fichiers sont composés de sections qui commencent par un en-tête `[section-name]`, suivi d’une liste d’entrées `key=value`.</span><span class="sxs-lookup"><span data-stu-id="293a9-138">These files are made up of sections which start with a `[section-name]` header, followed by a list of `key=value` entries.</span></span> <span data-ttu-id="293a9-139">Les noms de section respectent la casse, mais pas les noms de clés.</span><span class="sxs-lookup"><span data-stu-id="293a9-139">Section names are case-sensitive and key names are not.</span></span>
<span data-ttu-id="293a9-140">Les commentaires sont n’importe quelle ligne commençant par un `#` ou `;`.</span><span class="sxs-lookup"><span data-stu-id="293a9-140">Comments are any line that begins with a `#` or `;`.</span></span> <span data-ttu-id="293a9-141">Les commentaires inclus ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="293a9-141">Inline comments are not allowed.</span></span> <span data-ttu-id="293a9-142">Les valeurs booléennes ne respectent pas la casse et sont représentées par les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="293a9-142">Booleans are case-insensitive, and are represented by the following values.</span></span>

* <span data-ttu-id="293a9-143">__True__ : 1, yes, true, on</span><span class="sxs-lookup"><span data-stu-id="293a9-143">__True__: 1, yes, true, on</span></span>
* <span data-ttu-id="293a9-144">__False__ : 0, no, false, off</span><span class="sxs-lookup"><span data-stu-id="293a9-144">__False__: 0, no, false, off</span></span>

<span data-ttu-id="293a9-145">Voici un exemple de fichier de configuration d’interface CLI qui désactive les invites de confirmation et définit la journalisation sur le répertoire `/var/log/azure` actif.</span><span class="sxs-lookup"><span data-stu-id="293a9-145">Here's an example of a CLI configuration file which disables any confirmation prompts and sets up logging to the `/var/log/azure` directory.</span></span>

```
[core]
disable_confirm_prompt=Yes

[logging]
enable_log_file=yes
log_dir=/var/log/azure
```

<span data-ttu-id="293a9-146">Consultez la section suivante pour en savoir plus sur toutes les valeurs de configuration disponibles et leur signification.</span><span class="sxs-lookup"><span data-stu-id="293a9-146">See the next section for details on all of the available configuration values and what they mean.</span></span> <span data-ttu-id="293a9-147">Pour obtenir des informations détaillées sur le format de fichier INI, consultez la [documentation Python sur INI](https://docs.python.org/3/library/configparser.html#supported-ini-file-structure).</span><span class="sxs-lookup"><span data-stu-id="293a9-147">For the full details on the INI file format, see the [Python documentation on INI](https://docs.python.org/3/library/configparser.html#supported-ini-file-structure).</span></span>

## <a name="cli-configuration-values-and-environment-variables"></a><span data-ttu-id="293a9-148">Valeurs de configuration de l’interface CLI et variables d’environnement</span><span class="sxs-lookup"><span data-stu-id="293a9-148">CLI configuration values and environment variables</span></span>

<span data-ttu-id="293a9-149">Le tableau suivant contient l’ensemble des noms d’options et de sections pouvant être placés dans un fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="293a9-149">The following table contains all of the sections and option names that can be placed in a configuration file.</span></span> <span data-ttu-id="293a9-150">Les variables d’environnement correspondantes peuvent être définies en tant que `AZURE_{section}_{name}`, tout en majuscules.</span><span class="sxs-lookup"><span data-stu-id="293a9-150">Their corresponding environment variables can be set as `AZURE_{section}_{name}`, in all caps.</span></span> <span data-ttu-id="293a9-151">Par exemple, vous pouvez définir la valeur par défaut `storage_account` de la section `batchai` par défaut dans la variable `AZURE_BATCHAI_STORAGE_ACCOUNT`.</span><span class="sxs-lookup"><span data-stu-id="293a9-151">For example, you can set the `batchai` section's `storage_account` default in the `AZURE_BATCHAI_STORAGE_ACCOUNT` variable.</span></span>

<span data-ttu-id="293a9-152">La présence de toute valeur disposant d’une valeur par défaut n’est pas nécessaire dans les arguments de ligne de commande, même si elle est requise.</span><span class="sxs-lookup"><span data-stu-id="293a9-152">Any value with a default available does not have to be present in the command line arguments, even if it is required.</span></span>

| <span data-ttu-id="293a9-153">Section</span><span class="sxs-lookup"><span data-stu-id="293a9-153">Section</span></span> | <span data-ttu-id="293a9-154">NOM</span><span class="sxs-lookup"><span data-stu-id="293a9-154">Name</span></span>      | <span data-ttu-id="293a9-155">type</span><span class="sxs-lookup"><span data-stu-id="293a9-155">Type</span></span> | <span data-ttu-id="293a9-156">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="293a9-156">Description</span></span>|
|---------|-----------|------|------------|
| <span data-ttu-id="293a9-157">__core__</span><span class="sxs-lookup"><span data-stu-id="293a9-157">__core__</span></span> | <span data-ttu-id="293a9-158">sortie</span><span class="sxs-lookup"><span data-stu-id="293a9-158">output</span></span> | <span data-ttu-id="293a9-159">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-159">string</span></span> | <span data-ttu-id="293a9-160">Format de sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="293a9-160">The default output format.</span></span> <span data-ttu-id="293a9-161">Peut être `json`, `jsonc`, `tsv` ou `table`.</span><span class="sxs-lookup"><span data-stu-id="293a9-161">Can be one of `json`, `jsonc`, `tsv`, or `table`.</span></span> |
| | <span data-ttu-id="293a9-162">disable\_confirm\_prompt</span><span class="sxs-lookup"><span data-stu-id="293a9-162">disable\_confirm\_prompt</span></span> | <span data-ttu-id="293a9-163">booléenne</span><span class="sxs-lookup"><span data-stu-id="293a9-163">boolean</span></span> | <span data-ttu-id="293a9-164">Active/Désactive les invites de confirmation.</span><span class="sxs-lookup"><span data-stu-id="293a9-164">Turn confirmation prompts on/off.</span></span> |
| | <span data-ttu-id="293a9-165">collect\_telemetry</span><span class="sxs-lookup"><span data-stu-id="293a9-165">collect\_telemetry</span></span> | <span data-ttu-id="293a9-166">booléenne</span><span class="sxs-lookup"><span data-stu-id="293a9-166">boolean</span></span> | <span data-ttu-id="293a9-167">Autorise Microsoft à recueillir des données anonymes sur l’utilisation de l’interface CLI.</span><span class="sxs-lookup"><span data-stu-id="293a9-167">Allow Microsoft to collect anonymous data on the usage of the CLI.</span></span> <span data-ttu-id="293a9-168">Pour plus d’informations sur la confidentialité, consultez les [conditions d’utilisation d’Azure CLI 2.0](http://aka.ms/AzureCliLegal).</span><span class="sxs-lookup"><span data-stu-id="293a9-168">For privacy information, see the [Azure CLI 2.0 Terms of Use](http://aka.ms/AzureCliLegal).</span></span> |
| <span data-ttu-id="293a9-169">__logging__</span><span class="sxs-lookup"><span data-stu-id="293a9-169">__logging__</span></span> | <span data-ttu-id="293a9-170">enable\_log\_file</span><span class="sxs-lookup"><span data-stu-id="293a9-170">enable\_log\_file</span></span> | <span data-ttu-id="293a9-171">booléenne</span><span class="sxs-lookup"><span data-stu-id="293a9-171">boolean</span></span> | <span data-ttu-id="293a9-172">Active/Désactive la journalisation.</span><span class="sxs-lookup"><span data-stu-id="293a9-172">Turn logging on/off.</span></span> |
| | <span data-ttu-id="293a9-173">log\_dir</span><span class="sxs-lookup"><span data-stu-id="293a9-173">log\_dir</span></span> | <span data-ttu-id="293a9-174">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-174">string</span></span> | <span data-ttu-id="293a9-175">Répertoire dans lequel écrire les journaux.</span><span class="sxs-lookup"><span data-stu-id="293a9-175">The directory to write logs to.</span></span> <span data-ttu-id="293a9-176">(`${AZURE_CONFIG_DIR}/logs` par défaut).</span><span class="sxs-lookup"><span data-stu-id="293a9-176">By default this is `${AZURE_CONFIG_DIR}/logs`.</span></span> |
| <span data-ttu-id="293a9-177">__storage__</span><span class="sxs-lookup"><span data-stu-id="293a9-177">__storage__</span></span> | <span data-ttu-id="293a9-178">connection\_string</span><span class="sxs-lookup"><span data-stu-id="293a9-178">connection\_string</span></span> | <span data-ttu-id="293a9-179">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-179">string</span></span> | <span data-ttu-id="293a9-180">Chaîne de connexion par défaut à utiliser pour les commandes `az storage`.</span><span class="sxs-lookup"><span data-stu-id="293a9-180">The default connection string to use for `az storage` commands.</span></span> |
| | <span data-ttu-id="293a9-181">compte</span><span class="sxs-lookup"><span data-stu-id="293a9-181">account</span></span> | <span data-ttu-id="293a9-182">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-182">string</span></span> | <span data-ttu-id="293a9-183">Nom de compte par défaut à utiliser pour les commandes `az storage`.</span><span class="sxs-lookup"><span data-stu-id="293a9-183">The default account name to use for `az storage` commands.</span></span> |
| | <span data-ttu-id="293a9-184">key</span><span class="sxs-lookup"><span data-stu-id="293a9-184">key</span></span> | <span data-ttu-id="293a9-185">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-185">string</span></span> | <span data-ttu-id="293a9-186">Clé de compte par défaut à utiliser pour les commandes `az storage`.</span><span class="sxs-lookup"><span data-stu-id="293a9-186">The default account key to use for `az storage` commands.</span></span> |
| | <span data-ttu-id="293a9-187">sas\_token</span><span class="sxs-lookup"><span data-stu-id="293a9-187">sas\_token</span></span> | <span data-ttu-id="293a9-188">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-188">string</span></span> | <span data-ttu-id="293a9-189">Jeton SAS par défaut à utiliser pour les commandes `az storage`.</span><span class="sxs-lookup"><span data-stu-id="293a9-189">The default SAS token to use for `az storage` commands.</span></span> |
| <span data-ttu-id="293a9-190">__batchai__</span><span class="sxs-lookup"><span data-stu-id="293a9-190">__batchai__</span></span> | <span data-ttu-id="293a9-191">storage\_account</span><span class="sxs-lookup"><span data-stu-id="293a9-191">storage\_account</span></span> | <span data-ttu-id="293a9-192">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-192">string</span></span> | <span data-ttu-id="293a9-193">Compte de stockage par défaut à utiliser pour les commandes `az batchai`.</span><span class="sxs-lookup"><span data-stu-id="293a9-193">The default storage account to use for `az batchai` commands.</span></span> |
| | <span data-ttu-id="293a9-194">storage\_key</span><span class="sxs-lookup"><span data-stu-id="293a9-194">storage\_key</span></span> | <span data-ttu-id="293a9-195">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-195">string</span></span> | <span data-ttu-id="293a9-196">Clé de stockage par défaut à utiliser pour les commandes `az batchai`.</span><span class="sxs-lookup"><span data-stu-id="293a9-196">The default storage key to use for `az batchai` commands.</span></span> |
| <span data-ttu-id="293a9-197">__batch__</span><span class="sxs-lookup"><span data-stu-id="293a9-197">__batch__</span></span> | <span data-ttu-id="293a9-198">compte</span><span class="sxs-lookup"><span data-stu-id="293a9-198">account</span></span> | <span data-ttu-id="293a9-199">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-199">string</span></span> | <span data-ttu-id="293a9-200">Nom de compte Azure Batch par défaut à utiliser pour les commandes `az batch`.</span><span class="sxs-lookup"><span data-stu-id="293a9-200">The default Azure Batch account name to use for `az batch` commands.</span></span> |
| | <span data-ttu-id="293a9-201">access\_key</span><span class="sxs-lookup"><span data-stu-id="293a9-201">access\_key</span></span> | <span data-ttu-id="293a9-202">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-202">string</span></span> | <span data-ttu-id="293a9-203">Clé d’accès par défaut à utiliser pour les commandes `az batch`.</span><span class="sxs-lookup"><span data-stu-id="293a9-203">The default access key to use for `az batch` commands.</span></span> <span data-ttu-id="293a9-204">Uniquement utilisée avec l’autorisation `aad`.</span><span class="sxs-lookup"><span data-stu-id="293a9-204">Only used with `aad` authorization.</span></span> |
| | <span data-ttu-id="293a9-205">endpoint</span><span class="sxs-lookup"><span data-stu-id="293a9-205">endpoint</span></span> | <span data-ttu-id="293a9-206">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-206">string</span></span> | <span data-ttu-id="293a9-207">Point de terminaison par défaut auquel se connecter pour les commandes `az batch`.</span><span class="sxs-lookup"><span data-stu-id="293a9-207">The default endpoint to connect to for `az batch` commands.</span></span> |
| | <span data-ttu-id="293a9-208">auth\_mode</span><span class="sxs-lookup"><span data-stu-id="293a9-208">auth\_mode</span></span> | <span data-ttu-id="293a9-209">chaîne</span><span class="sxs-lookup"><span data-stu-id="293a9-209">string</span></span> | <span data-ttu-id="293a9-210">Mode d’autorisation à utiliser pour les commandes `az batch`.</span><span class="sxs-lookup"><span data-stu-id="293a9-210">The authorization mode to use for `az batch` commands.</span></span> <span data-ttu-id="293a9-211">Peut être `shared_key` ou `aad`.</span><span class="sxs-lookup"><span data-stu-id="293a9-211">Can be `shared_key` or `aad`.</span></span> |

> [!NOTE]
> <span data-ttu-id="293a9-212">Votre fichier de configuration peut contenir d’autres valeurs. Toutefois, celles-ci sont gérées directement par le biais de commandes de l’interface CLI, notamment `az configure`.</span><span class="sxs-lookup"><span data-stu-id="293a9-212">You may see other values in your configuration file, but these are managed directly through CLI commands, including `az configure`.</span></span> <span data-ttu-id="293a9-213">Les valeurs répertoriées dans le tableau ci-dessus sont les seules valeurs que vous devez modifier vous-même.</span><span class="sxs-lookup"><span data-stu-id="293a9-213">The ones listed in the table above are the only values you should change yourself.</span></span>