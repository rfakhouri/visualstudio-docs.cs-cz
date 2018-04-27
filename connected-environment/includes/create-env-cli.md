---
ms.topic: include
ms.openlocfilehash: 97f9885780c9f697cfc6a58b78054761fdcd725d
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
---
## <a name="create-a-kubernetes-development-environment-in-azure"></a>Vytvoření prostředí pro vývoj Kubernetes v Azure
S prostředím připojen můžete vytvořit na základě Kubernetes prostředí, které jsou plně spravované službou Azure a optimalizovaná pro vývoj. Příkaz vytvoří prostředí s názvem `mydevenvironment` v `eastus`.
```cmd
vsce env create --name mydevenvironment --location eastus
```

Podporované umístění: `eastus`, `westeurope`

> [!Note]
> Tento příkaz trvá přibližně 6 minut. Můžete pokračovat v této příručce bez čekání.
