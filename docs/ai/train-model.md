---
title: Tyto úlohy k natrénování modelu v Azure Batch AI
description: Train model cloudové
keywords: AI, visual studio, train model cloudu
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.devlang: multiple
ms.service: multiple
ms.technology: vs-ai-tools
ms.workload:
- azure
ms.openlocfilehash: ec0db69bbde1e2abab7022759ed0f7a3d2a88530
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="train-ai-models-in-azure-batch-ai"></a>Cvičení AI modely v Azure Batch AI

Batch AI je spravovaná služba, která umožňuje datových vědců a výzkumných pracovníků AI cvičení AI a dalších modelů strojového učení v clusterech virtuální počítače Azure, včetně virtuálních počítačů s podporou GPU. Popisuje požadavky na úlohy, kde můžete najít vstupní hodnoty a ukládají výstupy a Batch AI zpracovává zbytek. [Další informace o Azure Batch AI](https://docs.microsoft.com/azure/batch-ai/overview)

Je integrovaný s nástroji Visual Studio Tools pro AI tak dynamicky škálovat školení modely v Azure.  Jakmile jste [nainstalované Visual Studio Tools pro AI](installation.md), je snadné vytvořit nový projekt Python použití předem vytvořené recepty v galerii Azure Machine Learning ukázka.

1. Spusťte sadu Visual Studio. Otevřete **Průzkumníka serveru** otevřením **AI nástroje** nabídky a výběr **vyberte clusteru**

    ![Výběru clusteru](media\train-model\select-cluster.png)


2. Rozbalte položku **AI nástroje**. Všechny prostředky Batch AI, měli byste bude automaticky zjištěn a zobrazí v Průzkumníku serveru.

    ![Ukázka Galerie](media\train-model\batchai.png)

3. Vyberte **zobrazení > Team Explorer...**  otevřete **Team Explorer** okno, ve kterém můžete připojit k webu GitHub nebo Visual Studio Team Services, nebo klonovat úložiště.

    ![Team explorer okno zobrazující Visual Studio Team Services, GitHub a klonování úložiště](media\train-model\team-explorer.png)

4. Do pole Adresa URL v části **místní úložiště Git**, zadejte `https://github.com/Microsoft/samples-for-ai`, zadejte složku pro klonovaný soubory a vyberte **klon**.

    > [!Tip]
    > Složky, kterou zadáte v Team Explorer je konkrétní složky přijímat klonovaný soubory. Na rozdíl od `git clone` příkazu vytvoříte klon v Team Exploreru nevytvoří automaticky podsložku s názvem úložiště.

5. Po klonování je hotové, klikněte na tlačítko **soubor > Otevřít řešení > projekt nebo řešení**

    ![Ukázka Galerie](media\train-model\open-solution.png)

5. Otevřete **samples-for-ai\TensorFlowExamples\TensorFlowExamples.sln** v adresáři klonovat úložiště

    ![Ukázka Galerie](media\train-model\tensorflowexamples.png)

5. Sada MNIST projektu jako ** spouštěný projekt **

    ![Ukázka Galerie](media\train-model\mnist-startup.png)

1. ** Klikněte pravým tlačítkem na ** MNIST projektu **odeslat úlohu**

    ![Ukázka Galerie](media\train-model\submit-job.png)

1. Vyberte vaše **Azure Batch AI** clusteru a pak klikněte na **Import**. Vyberte `AzureBatchAI_TF_MNIST.json` souboru rychle naplní některé výchozí hodnoty, například která Docker Image použít. Pak klikněte na tlačítko **odeslání**

    ![Ukázka Galerie](media\train-model\submit-batch.png)