---
title: Jak používat kubectl s prostředím připojené | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 03/12/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 138dce09e0d53dc47703b9c6f56a7efda4adc255
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="use-kubectl-with-a-connected-environment"></a>Použití `kubectl` s připojeném prostředí

Má přístup ke clusteru Kubernetes v prostředí připojené, a použijte existující Kubernetes nástroje, jako `kubectl`.

Spuštění `vsce env create` nebo `vsce env select` automaticky přidá `kubectl` kontextu konfigurace pro vás, takže by již kubectl by měly být připojené ke clusteru VSCE Kubernetes. Příklady:
- Potvrďte aktuální kontext: `kubectl config current-context`
- Zobrazí seznam všech dostupných kontextů: `kubectl config get-contexts`. Cluster kubernetes vytvořené VSCE bude vypadat jako "vsce -<guid>".
- Změna kontextu: `kubectl config use-context <context-name>`
- Zobrazení řídicího panelu Kubernetes: Spusťte `kubectl proxy`, otevřete prohlížeč na adresu, kterou tento příkaz vysílá (připojit `/ui` na adresu URL, přejděte na řídicí panel Kubernetes).
- Seznam spuštění služeb ve výchozí místo VSCE s názvem *mainline*: `kubectl get services --namespace=mainline`

