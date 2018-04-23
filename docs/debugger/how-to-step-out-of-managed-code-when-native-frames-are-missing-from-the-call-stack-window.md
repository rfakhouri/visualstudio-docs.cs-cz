---
title: 'Postupy: vystoupení ze spravovaného kódu, pokud v okně zásobník volání chybějí nativní rámce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e21d45cd65fc6bc6a66f2f7c698952f0cdd788b9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>Postupy: Vystoupení ze spravovaného kódu, pokud v okně Zásobník volání chybějí nativní rámce.
Pokud má váš kód nativní rámce, které jsou v neviditelná **zásobníkem volání** okně krokování s mimo spravovaný kód může vést k neočekávaným výsledkům. Jako alternativní řešení, můžete použít zarážku místo **Krokovat s Vystoupením**.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>Chcete-li vystoupení ze spravovaného kódu, pokud zobrazení zásobník volání chybějí nativní rámce  
  
1.  V nativním kódu zarážku umístění po volání do spravovaného kódu.  
  
2.  Na **ladění** nabídce zvolte **pokračovat**.  
  
     Po dokončení volání spravované provádění zastaví u zarážky v nativním kódu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md)