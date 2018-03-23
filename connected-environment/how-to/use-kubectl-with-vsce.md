---
title: Jak používat kubectl s prostředím připojené | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 03/12/2018
ms.topic: article
ms.technology: vsce-kubernetes
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: ghogen
ms.openlocfilehash: 46c69f80e58a4265aa5e4320e731c3ad241a8116
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="use-kubectl-with-a-connected-environment"></a>Použití `kubectl` s připojeném prostředí

Má přístup ke clusteru Kubernetes v prostředí připojené, a použijte existující Kubernetes nástroje, jako `kubectl`.

Spuštění `vsce env create` nebo `vsce env select` automaticky přidá `kubectl` kontextu konfigurace pro vás, takže by již kubectl by měly být připojené ke clusteru VSCE Kubernetes. Příklady:
- Potvrďte aktuální kontext: `kubectl config current-context`
- Zobrazí seznam všech dostupných kontextů: `kubectl config get-contexts`. Cluster kubernetes vytvořené VSCE bude vypadat jako "vsce -<guid>".
- Změna kontextu: `kubectl config use-context <context-name>`
- Zobrazení řídicího panelu Kubernetes: Spusťte `kubectl proxy`, otevřete prohlížeč na adresu, kterou tento příkaz vysílá (připojit `/ui` na adresu URL, přejděte na řídicí panel Kubernetes).
- Seznam spuštění služeb ve výchozí místo VSCE s názvem *mainline*: `kubectl get services --namespace=mainline`

