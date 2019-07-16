---
title: 'Postupy: Automatické použití kódů product key při nasazení sady Visual Studio 2015 | Dokumentace Microsoftu'
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
caps.latest.revision: 11
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: ec050cf8f365bfae2290593a0c7f215dcb2f39cc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68185996"
---
# <a name="how-to-automatically-apply-product-keys-when-deploying-visual-studio"></a>Postupy: Automatické použití kódů Product Key při nasazení sady Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [automatické použití kódů product key při nasazení sady Visual Studio](/visualstudio/install/automatically-apply-product-keys-when-deploying-visual-studio).

Můžete použít kód product key prostřednictvím kódu programu jako součást skriptu použít k automatizaci nasazení sady Visual Studio 2015. Kódy Product Key můžete nastavit na zařízení prostřednictvím kódu programu při instalaci sady Visual Studio nebo po dokončení instalace.

## <a name="apply-the-license-during-installation"></a>Použití licence během instalace
 Chcete-li použít kód product key během procesu instalace sady Visual Studio, použijte parametr/ProductKey. Tento parametr instalace lze použít s/silent parametr instalace sady Visual Studio ve stavu již licencované pro koncového uživatele. Pokud chcete použít parametr/ProductKey, otevřete příkazový řádek. Spusťte instalační program (například vs_enterprise.exe nebo vs_professional.exe) a nastavte parametr/ProductKey s kódem product key (25 znaků), který obsahuje pomlčky:

 Toto je příklad příkaz pro instalaci sady Visual Studio 2015 Enterprise s kódem product key AAAAABBBBBCCCCCDDDDDEEEEEEE:

 `vs_enterprise.exe [any other setup parameters] /ProductKey AAAAABBBBBCCCCCDDDDDDEEEEEE`

## <a name="apply-the-license-after-installation"></a>Použití licence, které jsou po instalaci
 Nainstalovaná verze sady Visual Studio s kódem product key můžete aktivovat pomocí nástroje storePID.exe na cílové počítače v bezobslužném režimu. StorePID.exe program je nástroj, který instaluje se sadou Visual Studio na  **\<jednotky >:\\\Program soubory (x86) \Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe**.

 StorePID.exe spusťte s vyššími oprávněními, buď pomocí agenta System Center nebo příkazovém řádku, za nímž následuje kód product key (včetně pomlček) a kód produktu společnosti Microsoft (MPC). Nezapomeňte zahrnout pomlček kód product key!

 `StorePID.exe [product key including the dashes] [MPC]`

 Toto je příklad příkazového řádku pro instalaci Visual Studio Enterprise 2015, který má MPC 07060 s kódem product key "AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE":

 `C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 07060`

 V následující tabulce jsou uvedeny kódy MPC pro jednotlivé edice aplikace Visual Studio:

|Edice sady Visual Studio|MPC|
|---------------------------|---------|
|Visual Studio Enterprise 2015|07060|
|Visual Studio Professional 2015|07062|
|Visual Studio Test Professional 2015|07066|
|Visual Studio Ultimate 2013|06181|
|Visual Studio Premium 2013|06191|
|Visual Studio Professional 2013|06177|
|Visual Studio Test Professional 2013|06194|

Další informace o získání kódu product key, naleznete v tématu [jak: Vyhledejte kód Product Key sady Visual Studio](../install/how-to-locate-the-visual-studio-product-key.md).

Pokud StorePID.exe úspěšně použít kód product key, vrátí 0. Pokud se setká chyby, vrátí číslo od 1 do 6.

## <a name="see-also"></a>Viz také:

- [Instalace sady Visual Studio](../install/install-visual-studio-2015.md)