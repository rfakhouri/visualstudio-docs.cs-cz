---
title: "Cvičení modelu tensorflow místně"
description: "Tensorflow model spustit místně v AI nástrojů pro Visual Studio"
keywords: "AI, visual studio, tensorflow, místní"
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: quickstart
ms.technology: visual studio
ms.devlang: python
ms.service: multiple
ms.openlocfilehash: 2b48acc8cfea97a89c32ce7180d693246ca6ab26
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="train-a-tensorflow-model-locally"></a>Cvičení modelu TensorFlow místně 

V tento rychlý start, jsme se trénují podle nich model TensorFlow s [MNIST](http://yann.lecun.com/exdb/mnist/) datovou sadu místně v Visual Studio Tools for AI. Databázi MNIST má sadu 60 000 příklady školení a testovací sadu 10 000 příklady psané číslic. 

## <a name="prerequisites"></a>Požadavky

Než začnete, ujistěte se, že máte nainstalované tyto položky:

### <a name="google-tensorflow"></a>Google TensorFlow 

Spusťte následující příkaz v terminálu. 
```cmd
C:\>pip.exe install tensorflow
```

### <a name="numpy-and-scipy"></a>NumPy a SciPy 
Nainstalujte [NumPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy) a [SciPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy). 

### <a name="download-sample-code"></a>Stáhněte si ukázkový kód
Stáhněte si to [úložiště GitHub](https://github.com/Microsoft/samples-for-ai) obsahující ukázky pro zahájení práce s hloubkovým learning napříč TensorFlow, CNTK, Theano a další. 

## <a name="open-solution-and-train-model"></a>Otevřete řešení a cvičení modelu

- Spusťte sadu Visual Studio a vyberte **soubor > Otevřít > projekt nebo řešení**.

- Vyberte **Tensorflow příklady** složky z ukázky úložiště staženy a otevřete **TensorflowExamples.sln** souboru. 

![Otevřít projekt](media\tensorflow-local\open-project.png)

![Otevřít řešení](media\tensorflow-local\open-solution.png)

- Najít projekt MNIST v **Průzkumníku řešení**, klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.

- Klikněte na tlačítko **spustit**. 

- Výstup je vytištěna v konzole.

![Ukázkový výstup z konzoly](media\tensorflow-local\console-output.png)

> [!div class="nextstepaction"]
> [Cvičení modelu TensorFlow v cloudu](tensorflow-vm.md)