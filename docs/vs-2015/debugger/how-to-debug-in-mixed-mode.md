---
title: 'Postupy: Ladění ve smíšeném režimu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5e4a20faa34e8d0dd1018cb4cb5ee0a6df098177
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60107187"
---
# <a name="how-to-debug-in-mixed-mode"></a>Postupy: Ladění ve smíšeném režimu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Následující postupy popisují, jak ladit spravované i nativní kód, označované také jako ladění ve smíšeném režimu. Existují dva scénáře to udělat, v závislosti na tom, zda je knihovna DLL nebo aplikace napsány v nativním kódu:  
  
- Volající aplikace, která volá vaši knihovnu DLL je napsány v nativním kódu. V tomto případě spravuje vaše knihovna DLL a spravované i nativní ladicí programy musí být povoleno ladění i. Můžete to zkontrolovat  **\<Projekt > stránky vlastností** dialogové okno. Postup závisí na tom, zda spustíte ladění z projektu knihovny DLL nebo projekt volající aplikace.  
  
- Volající aplikace, která volá vaši knihovnu DLL je zapsána ve spravovaném kódu a vaše knihovna DLL je zapsaný v nativním kódu.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-enable-mixed-mode-debugging"></a>Pokud chcete povolit ladění ve smíšeném režimu  
  
1. V **Průzkumníka řešení**, vyberte projekt.  
  
2. Na **zobrazení** nabídky, klikněte na tlačítko **stránky vlastností**.  
  
3. V  **\<Projekt > stránky vlastností** dialogového okna rozbalte **vlastnosti konfigurace** uzlu a pak vyberte **ladění**.  
  
4. Nastavte **typ ladicího programu** k **smíšené** nebo **automaticky**.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Ladění projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md)
