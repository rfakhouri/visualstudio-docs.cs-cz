---
title: Trénování tensorflow modelu místně
description: Tensorflow model spuštěna místně ve nástroje AI pro sadu Visual Studio
keywords: AI, visual studio, tensorflow, místní
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: quickstart
ms.devlang: python
ms.workload:
- multiple
ms.openlocfilehash: 26668247bf993da3eb3f2803abaf9288e566ffee
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62555453"
---
# <a name="train-a-tensorflow-model-locally"></a>Trénování TensorFlow modelu místně

V tomto rychlém startu jsme se trénování TensorFlow model se [mnist ručně](http://yann.lecun.com/exdb/mnist/) datovou sadu místně v aplikaci Visual Studio Tools pro AI.

Databázi mnist ručně má trénovací sady 60 000 příkladů a testovací sadu 10 000 příklady rukou psaný číslic.

## <a name="prerequisites"></a>Požadavky

Než začnete, ujistěte se, že máte nainstalované tyto položky:

### <a name="google-tensorflow"></a>Google TensorFlow

V terminálu spusťte následující příkaz:

```cmd
C:\>pip.exe install tensorflow
```

### <a name="numpy-and-scipy"></a>NumPy a SciPy
Nainstalujte [NumPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy) a [SciPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy).

### <a name="download-sample-code"></a>Stáhněte si ukázkový kód
Stáhněte si tuto aplikaci [úložiště GitHub](https://github.com/Microsoft/samples-for-ai) obsahující ukázky pro zahájení práce s hloubkového učení napříč TensorFlow, CNTK, Theano a další.

## <a name="open-solution-and-train-model"></a>Otevřete řešení a jejich trénování modelu

- Spusťte sadu Visual Studio a vyberte **soubor > Otevřít > Projekt/řešení**.

- Vyberte **Tensorflow příklady** složku z úložiště ukázek stažený a otevřít **TensorflowExamples.sln** souboru.

   ![Otevřený projekt](media/tensorflow-local/open-project.png)

   ![Otevřít řešení](media/tensorflow-local/open-solution.png)

- Najít projekt mnist ručně v **Průzkumníka řešení**klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.

- Klikněte na tlačítko **Start**.

- Výstup je vytištěna v konzole.

   ![Ukázkový výstup z konzoly](media/tensorflow-local/console-output.png)

> [!div class="nextstepaction"]
> [Trénování TensorFlow modelu v cloudu](tensorflow-vm.md)