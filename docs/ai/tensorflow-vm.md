---
title: Spustit TensorFlow model v cloudu
description: spustíte tensorflow model v azure hloubkového učení virtuálního počítače
keywords: AI, visual studio, obsáhlý learning virtuálního počítače
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: tutorial
ms.devlang: python
ms.workload:
- multiple
ms.openlocfilehash: adb3720f1624f355b99d75bfe446fafab1c5e0ae
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62427543"
---
# <a name="train-a-tensorflow-model-in-the-cloud"></a>Trénování TensorFlow modelu v cloudu

V tomto kurzu jsme se trénování TensorFlow pomocí modelu [datovou sadu mnist ručně](http://yann.lecun.com/exdb/mnist/) na Azure [obsáhlého learningu](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/deep-learning-dsvm-overview) virtuálního počítače.

Databázi mnist ručně má trénovací sady 60 000 příkladů a testovací sadu 10 000 příklady rukou psaný číslic.

## <a name="prerequisites"></a>Požadavky
Než začnete, zkontrolujte, že máte nainstalovanou a nakonfigurovanou následující:

### <a name="setup-azure-deep-learning-virtual-machine"></a>Nastavení Azure pro hloubkové učení virtuálního počítače

> [!NOTE]
> Nastavte **typ operačního systému** na Linuxu.

Najdete pokyny pro nastavení se virtuální počítač pro hloubkové učení [tady](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/provision-deep-learning-dsvm).

### <a name="remove-comment-in-parens"></a>Odebrat komentář parens

```bash
echo -e ". /etc/profile\n$(cat ~/.bashrc)" > ~/.bashrc
```

### <a name="download-sample-code"></a>Stáhněte si ukázkový kód

Stáhněte si tuto aplikaci [úložiště GitHub](https://github.com/Microsoft/samples-for-ai) obsahující ukázky pro zahájení práce s obsáhlého learningu na TensorFlow, CNTK, Theano a další.

## <a name="open-project"></a>Otevřený projekt

- Spusťte sadu Visual Studio a vyberte **soubor > Otevřít > Projekt/řešení**.

- Vyberte **Tensorflow příklady** složku z úložiště ukázek stažený a otevřít **TensorflowExamples.sln** souboru.

   ![Otevřený projekt](media/tensorflow-local/open-project.png)

   ![Otevřít řešení](media/tensorflow-local/open-solution.png)

## <a name="add-azure-remote-vm"></a>Přidat vzdáleném virtuálním počítači Azure

V Průzkumníku serveru, klikněte pravým tlačítkem myši **vzdálených počítačů** uzel v uzlu nástroje AI a vyberte "přidat...". Zadejte zobrazovaný název vzdáleného počítače, IP hostitele, SSH port, uživatelské jméno a heslo/klíč souboru.

![Přidat nový vzdálený počítač](media/tensorflow-vm/add-remote-vm.png)

## <a name="submit-job-to-azure-vm"></a>Odeslat úlohu do virtuálního počítače Azure
Klikněte pravým tlačítkem na projekt mnist ručně v **Průzkumníka řešení** a vyberte **odeslat úlohu**.

![Odeslání úlohy ke vzdálenému počítači](media/tensorflow-vm/job-submission.png)

V okně odeslání:

- V seznamu **Cluster používat**, vyberte vzdálený počítač (pomocí "rm:" předpony) se odeslat úlohu do.

- Zadejte **název úlohy**.

- Klikněte na **Submit** (Odeslat).

## <a name="check-status-of-job"></a>Zkontrolujte stav úlohy
Zobrazit stav a podrobnosti úlohy: rozbalte virtuální počítač, který jste odeslali úlohu v **Průzkumníka serveru**. Dvakrát klikněte na **úlohy**.

![Prohlížeč úloh](media/tensorflow-vm/job-browser.png)

## <a name="clean-up-resources"></a>Vyčištění prostředků

Zastavte virtuální počítač, pokud máte v úmyslu používat v blízké budoucnosti. Pokud budete mít v tomto kurzu, spusťte následující příkaz pro vyčištění prostředků:

```azurecli-interactive
az group delete --name myResourceGroup
```
