---
title: Instalace AI nástrojů pro Visual Studio
description: Instalace AI nástrojů pro Visual Studio
keywords: AI, visual studio
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.devlang: multiple
ms.service: multiple
ms.technology: vs-ai-tools
ms.workload:
- multiple
ms.openlocfilehash: 93e28558b1d09ded8de5bc6c4eb45230435cb807
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="installation"></a>Instalace

Nástroje sady Visual Studio pro AI lze nainstalovat v operačních systémech Windows 64-bit.

## <a name="installing-visual-studio-tools-for-ai"></a>Instalace nástrojů Visual Studio Tools pro AI

Toto rozšíření pracuje s [Visual Studio](https://docs.microsoft.com/visualstudio/) 2015, 2017, Community edition nebo vyšší.

Pokud chcete nainstalovat, stáhnout z [Visual Studio MarketPlace](http://aka.ms/vstoolsforai) nebo z v sadě Visual Studio

1. **Nástroje pro**> **rozšíření a aktualizace**

![Nainstalujte CUDA v systému Windows](media\installation\extensions.png)

1. **Hledání** v horním pravém rohu pro "Nástroje pro AI"
2. Vyberte **Visual Studio Tools pro AI**
3. Klikněte na tlačítko **stáhnout**


## <a name="preparing-your-local-machine"></a>Příprava místního počítače

Před školení hloubkové učení modely v místním počítači, které byste měli mít nejnovější použít nainstalovány požadované součásti. To je potřeba zajistit, že nejnovější ovladače a knihovny pro vaše NVIDIA grafický procesor (pokud nějaký máte). Také se ujistěte, jste nainstalovali Python a Python knihovny například NumPy, SciPy a příslušné přímým učení architektury, jako je například Microsoft kognitivní Toolkit (CNTK), TensorFlow, Caffe2, MXNet, Keras, Theano, PyTorch nebo zřetězeného souboru, který chcete použít ve vašem projektu.

> [!NOTE]
>
> Úvod softwaru v následující podčásti je převzat z jejich domovské stránky webových stránek.

### <a name="nvidia-gpu-driver"></a>Ovladač NVIDIA GPU

Hloubkové learning architektury využít výhod NVIDIA GPU umožníte počítače další rychlostí, přesnost a škálování směrem true umělé inteligence. Pokud váš počítač karty NVIDIA, navštivte [sem](http://www.nvidia.com/Download/index.aspx) nebo se pokuste OS update nainstalujte nejnovější ovladače.

### <a name="cuda"></a>CUDA

[CUDA](https://developer.nvidia.com/cuda-zone) je paralelní výpočty platformy a programovací model vyvinuta firmou NVIDIA.
Umožňuje výraznému nárůstu využití výkonu, neboť využití možností GPU.
V současné době CUDA Toolkit 8.0 vyžaduje hloubkové learning architektury.

Chcete-li nainstalovat CUDA

- Získáte na tomto [lokality](https://developer.nvidia.com/cuda-80-ga2-download-archive), CUDA stáhněte a nainstalujte ho.
- Zajistěte, aby k instalaci modulu runtime knihoven CUDA a poté přidejte CUDA binární cesta k % cesta % nebo $Path proměnné prostředí.
- V systému Windows je tato cesta "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v8.0\bin" ve výchozím nastavení.

![Nainstalujte CUDA v systému Windows](media\installation\install_cuda_win.png)

### <a name="cudnn"></a>cuDNN

[cuDNN](https://developer.nvidia.com/cudnn) (knihovna CUDA hluboké Neuronové sítě) je knihovna GPU accelerated primitivních elementů pro hluboké neuronové sítě pomocí NVIDIA. je požadován cuDNN v6 nejnovější hloubkové learning architektury.

Chcete-li nainstalovat cuDNN
- Navštivte [sem](https://developer.nvidia.com/rdp/cudnn-download) stáhnout a nainstalovat nejnovější balíček.
- Ujistěte se, chcete-li přidat adresář obsahující cuDNN binární k % % nebo $Path proměnné prostředí PATH.
- V systému Windows můžete zkopírovat cudnn64_6.dll do "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v8.0\bin".

> [!NOTE]
>
> Předchozí hloubkové learning architektury, jako je například CNTK 2.0 a TensorFlow 1.2.1 potřebovat verze 5.1 cuDNN.
> Můžete však nainstalovat několik verzí cuDNN společně.


### <a name="python"></a>Python

Python byl primární programovací jazyk pro přímý learning aplikací.
**64-bit** je požadováno, distribuci jazyka Python a [Python 3.5.4](https://www.python.org/downloads/release/python-354/) se doporučuje pro nejlepší kompatibility.

### <a name="to-install-python-on-windows"></a>K instalaci Pythonu na systému Windows
- Jsme navrhne pouze instalace Spouštěč jazyka Python pro sami a přidejte do proměnné prostředí % PATH % Python.
- Ujistěte se, chcete-li nainstalovat pip, který je systém správy balíčků, instalaci a správě softwarových balíčků, které jsou napsané v Pythonu.

Hloubkové learning rozhraní závisí na pip pro vlastní instalaci.

![Instalace jazyka Python v systému Windows](media\installation\install_python_win.png)

Pak je potřeba ověřit, zda je správně nainstalován jazyk Python 3.5 a pip upgradovat na nejnovější verzi spuštěním následujících příkazů v terminálu:

- **Windows**
    ```cmd
    C:\Users\test>python -V
    Python 3.5.4

    C:\Users\test>pip3.5 -V
    pip 9.0.1 from c:\users\test\appdata\local\programs\python\python35\lib\site-packages (python 3.5)

    C:\Users\test>python -m pip install -U pip
    ```

- **macOS**
    ```bash
    MyMac:~ test$ python3.5 -V
    Python 3.5.4

    MyMac:~ test$ pip3.5 -V
    pip 9.0.1 from /Library/Frameworks/Python.framework/Versions/3.5/lib/python3.5/site-packages (python 3.5)

    MyMac:~ test$ python3.5 -m pip install -U pip
    ```

### <a name="python-on-visual-studio"></a>Python v sadě Visual Studio

Python je plně podporovaný v sadě Visual Studio prostřednictvím rozšíření.
Další informace o instalaci [Python pro Visual Studio Tools](../python/installing-python-support-in-visual-studio.md) další podrobnosti.

### <a name="numpy-and-scipy"></a>NumPy a SciPy

- **NumPy** je navržený tak, aby efektivně pracovat s velké vícerozměrných polí záznamů libovolný zároveň zachovávají příliš mnoho rychlost pro malé vícerozměrných polí pro obecné účely pole zpracování balíček.

- **SciPy** (vyslovováno "Sigh kruhový") je open-source softwaru pro Matematika, vědecké účely a technologie, v závislosti na NumPy.
Od verze 1.0.0, SciPy má nyní oficiální předem wheel balíčku pro systém Windows.

Chcete-li nainstalovat NumPy a SciPy, spusťte následující příkaz v terminálu:
```bash
pip3.5 install -U numpy scipy
```

> [!NOTE]
>
> Výše uvedený příkaz upgrady existující staré nebo neoficiální (například balíčky jiných výrobců z http://www.lfd.uci.edu/~gohlke/pythonlibs/ pro Windows) NumPy a SciPy na nejnovější oficiální ty.

### <a name="microsoft-cognitive-toolkit-cntk"></a>Sada nástrojů pro kognitivní (CNTK)

[Kognitivní nástrojů Microsoft](https://cntk.ai) je jednotná nástrojů přímým learning popisuje neuronové sítě jako řadu výpočetní kroky prostřednictvím orientovaného grafu. CNTK podporuje Python a BrainScript programovacích jazyků.

> [!NOTE]
>
> CNTK aktuálně nepodporuje systému macOS.

Chcete-li instalovat balíček CNTK Python, přečtěte si téma [postup instalace CNTK](https://docs.microsoft.com/cognitive-toolkit/Setup-CNTK-on-your-machine)

### <a name="tensorflow"></a>TensorFlow

[TensorFlow](https://www.tensorflow.org/) je knihovna software s otevřeným zdrojem pro číselné výpočty pomocí grafů datového toku.
Odkazovat na [sem](https://www.tensorflow.org/install/) pro podrobné instalaci.

> [!NOTE]
>
> Od verze 1.2 TensorFlow už podporuje grafický procesor systému macOS.

### <a name="caffe2"></a>Caffe2

[Caffe2](https://caffe2.ai/) je jednoduché, modulární a škálovatelné hloubkové learning rozhraní.
Sestavování na původní Caffe, Caffe2 slouží s výrazem, rychlostí a modularitu v paměti.

V současné době není k dispozici žádné předem připraveného Caffe2 python wheel balíčku.

Navštivte [sem](https://caffe2.ai/docs/getting-started.html) k sestavení ze zdrojového kódu.

### <a name="mxnet"></a>MXNet

[Apache MXNet (inkubaci)](https://mxnet.incubator.apache.org/) je hloubkové learning rozhraní určené pro efektivitu a flexibilitu.
Umožňuje **kombinovat** [symbolický a imperativní programování](http://mxnet.io/architecture/index.html#deep-learning-system-design-concepts) maximalizovat efektivitu a produktivitu.

Pokud chcete nainstalovat MXNet, spusťte následující příkaz v terminálu:
- S grafickým Procesorem
    ```bash
    pip3.5 install mxnet-cu80==0.12.0
    ```
- Bez GPU
    ```bash
    pip3.5 install mxnet==0.12.0
    ```

### <a name="keras"></a>Keras

[Keras](https://keras.io/) je napsané v Pythonu a může spustit v horní části CNTK, TensorFlow nebo Theano rozhraní API vysoké úrovně neuronové sítě. Byl vyvinut se zaměřením na povolení rychlého experimenty. Schopnost přechod z je vhodné vést s nejmenšími možnými zpoždění je klíčem k provádění dobrý research.

Pokud chcete nainstalovat Keras, spusťte následující příkaz v terminálu:
```bash
pip3.5 install Keras==2.0.9
```

### <a name="theano"></a>Theano

[Theano](http://deeplearning.net/software/theano/) je knihovna Python, který umožňuje definovat, optimalizace a vyhodnotit matematické výrazy efektivně zahrnující vícerozměrných polí.

Pokud chcete nainstalovat Theano, spusťte následující příkaz v terminálu:
```bash
pip3.5 install Theano==0.9.0
```

### <a name="pytorch"></a>PyTorch

[PyTorch](http://pytorch.org/) je balíček python, který poskytuje dvě základní funkce:
- Výpočet tensor (např. numpy) s silné akcelerace GPU
- Hluboké Neuronové sítě založený na systému autograd založené na pásce

Pokud chcete nainstalovat PyTorch, spusťte následující příkaz v terminálu:

- **Windows**
    - Není zatím žádná oficiální wheel balíčku. Můžete ho stáhnout třetích stran [Anaconda PyTorch balíček](https://anaconda.org/peterjc123/pytorch/0.2.1/download/win-64/pytorch-0.2.1-py35h24644ff_0.2.1cu80.tar.bz2).
    - Dekomprese domovskému adresáři, například "C:\Users\test\pytorch".
    - Přidejte proměnnou prostředí % PYTHONPATH % "C:\Users\test\pytorch\Lib\site-packages".

- **macOS**
    ```bash
    pip3.5 install http://download.pytorch.org/whl/torch-0.2.0.post3-cp35-cp35m-macosx_10_7_x86_64.whl
    ```
    > [!NOTE]
    >
    > binární soubory systému macOS nemusíte podporovat CUDA, nainstalovat ze zdroje, pokud je potřeba CUDA

- **Linux**
    ```bash
    pip3.5 install http://download.pytorch.org/whl/cu80/torch-0.2.0.post3-cp35-cp35m-manylinux1_x86_64.whl
    ```
    > [!NOTE]
    >
    > Jeden balíček podporuje GPU a procesoru.

Nakonec torchvision nainstalujte na jiný systém než Windows:
```bash
pip3.5 install torchvision
```

### <a name="chainer"></a>Zřetězeného souboru

[Zřetězeného souboru](https://chainer.org/) je rozhraní na základě Python hloubkové learning zaměřené na flexibilitu.
Poskytuje automatické rozdílů mezi založené na rozhraní API **definovat pomocí spustit přístup** (také známa jako dynamické výpočetní grafy) a také objektově orientované vysoké úrovně rozhraní API pro sestavení a cvičení neuronové sítě.

Chcete-li povolit podporu CUDA, nainstalovat [CuPy](https://github.com/cupy/cupy):
```bash
pip3.5 install cupy
```

> [!NOTE]
>
> V systému Windows, musíte **2015** verzi [Microsoft Visual Studio](https://www.visualstudio.com/) nebo [Microsoft Visual C++ nástroje sestavení](http://landinghub.visualstudio.com/visual-cpp-build-tools) zkompilovat CuPy s CUDA 8.0.

Pokud chcete nainstalovat zřetězeného souboru, spusťte následující příkaz v terminálu:
```bash
pip3.5 install chainer==3.0.0
```


