---
title: Spustit TensorFlow model v cloudu
description: "Spusťte tensorflow model v azure hloubkové učení virtuálních počítačů"
keywords: "AI, visual studio, hloubkové učení virtuálního počítače"
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: tutorial
ms.devlang: python
ms.service: multiple
ms.technology: vs-ai-tools
ms.workload:
- multiple
ms.openlocfilehash: 1f02a03ca314138715b46e098416c7eef49e6d72
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="train-a-tensorflow-model-in-the-cloud"></a>Cvičení modelu TensorFlow v cloudu

V tomto kurzu jsme se trénování modelu TensorFlow pomocí [datovou sadu MNIST](http://yann.lecun.com/exdb/mnist/) v Azure [hloubkové Learning](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/deep-learning-dsvm-overview) virtuálního počítače.

Databázi MNIST má sadu 60 000 příklady školení a testovací sadu 10 000 příklady psané číslic.

## <a name="prerequisites"></a>Požadavky
Než začnete, ujistěte se, že máte k dispozici následující nainstalovaný a nakonfigurovaný:

### <a name="setup-azure-deep-learning-virtual-machine"></a>Instalační program Azure přímým učení virtuálního počítače

> [!NOTE]
> Nastavit **typ operačního systému** do systému Linux.

Pokyny pro nastavení nahoru hloubkové Learning virtuálního počítače lze nalézt [zde](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/provision-deep-learning-dsvm).

### <a name="remove-comment-in-parens"></a>Odebrat komentář ve parens

```bash
echo -e ". /etc/profile\n$(cat ~/.bashrc)" > ~/.bashrc
```

### <a name="download-sample-code"></a>Stáhněte si ukázkový kód

Stáhněte si to [úložiště GitHub](https://github.com/Microsoft/samples-for-ai) obsahující ukázky pro zahájení práce s hloubkovým learning napříč TensorFlow, CNTK, Theano a další.

## <a name="open-project"></a>Otevřít projekt

- Spusťte sadu Visual Studio a vyberte **soubor > Otevřít > projekt nebo řešení**.

- Vyberte **Tensorflow příklady** složky z ukázky úložiště staženy a otevřete **TensorflowExamples.sln** souboru.

![Otevřít projekt](media\tensorflow-local\open-project.png)

![Otevřít řešení](media\tensorflow-local\open-solution.png)

## <a name="add-azure-remote-vm"></a>Přidat vzdálené virtuálních počítačů Azure

V Průzkumníku serveru, klikněte pravým tlačítkem **vzdálených počítačích** uzel v rámci nástroje AI uzel a vyberte možnost "přidat...". Zadejte zobrazovaný název vzdáleného počítače, IP hostitele, SSH port, uživatelské jméno a heslo nebo klíč souboru.

![Přidání nového vzdáleného počítače](media\tensorflow-vm\add-remote-vm.png)

## <a name="submit-job-to-azure-vm"></a>Odeslání úlohy na virtuálním počítači Azure
Klikněte pravým tlačítkem na projekt MNIST v **Průzkumníku řešení** a vyberte **odeslat úlohu**.

![Odeslání úlohy ke vzdálenému počítači](media\tensorflow-vm\job-submission.png)

V okně odeslání:

- V seznamu **clusteru, aby používaly**, vyberte vzdáleného počítače (s "rm:" předpona) se odeslat úlohu k.

- Zadejte **název úlohy**.

- Klikněte na tlačítko **odeslání**.

## <a name="check-status-of-job"></a>Zkontrolujte stav úlohy
Chcete-li zobrazit stav a podrobnosti o úlohách: rozbalte virtuálního počítače, které jste odeslali úlohu, která má v **Průzkumníka serveru**. Dvakrát klikněte na **úlohy**.

![Úloha prohlížeče](media\tensorflow-vm\job-browser.png)

## <a name="clean-up-resources"></a>Vyčištění prostředků

Zastavte virtuální počítač, pokud máte v úmyslu používat ho v blízké budoucnosti. Po dokončení tohoto kurzu, spusťte následující příkaz k vyčištění vaše prostředky:

```azurecli-interactive
az group delete --name myResourceGroup
```