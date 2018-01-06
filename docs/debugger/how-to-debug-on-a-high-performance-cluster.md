---
title: "Postupy: ladění na clusteru, vysoce výkonné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- cluster debugging
- high-perfomance debugging
ms.assetid: a2f0eb07-840e-4f95-a1b1-9509217e5b8f
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 18a8d66da62fd480934c750a6b809465022c5d6b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-on-a-high-performance-cluster"></a>Postupy: Ladění na klastru s vysokým výkonem
Program multiprocesing na clusteru, vysoce výkonné ladění je jako ladění normální program na vzdáleném počítači. Existuje však několik dalších důležitých informací. Obecné nastavení vzdálené požadavky najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
 Při ladění na clusteru, vysoce výkonné, můžete použít všechny [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladění windows a techniky, které jsou k dispozici pro vzdálené ladění. Vzhledem k tomu, že ladíte vzdáleně, ale v okně konzoly externí není k dispozici.  
  
 **Vláken** okno a **procesy** okna jsou užitečné zejména pro ladění paralelní aplikace. Tipy pro používání těchto windows najdete v tématu [postupy: použití okna procesy](http://msdn.microsoft.com/en-us/0207ce2f-8ceb-4fe7-b2b5-4dd35b035ed7) a [návod: ladění pomocí okna vláken](../debugger/how-to-use-the-threads-window.md).  
  
 Následující postupy popisují některé techniky, které jsou užitečné zejména pro ladění na clusteru s podporou vysoce výkonné.  
  
 Při ladění paralelní aplikace, můžete chtít nastavit zarážky konkrétní vlákno, procesu nebo počítače. Můžete provést vytvořením normální zarážek a následným přidáním zarážek filtru.  
  
### <a name="to-open-the-breakpoint-filter-dialog-box"></a>Chcete-li otevřít dialogové okno zarážek filtru  
  
1.  Klikněte pravým tlačítkem na glyf zarážek v okně zdroje **zpětný překlad** okně **zásobníkem volání** okno, nebo **zarážky** okno.  
  
2.  V místní nabídce klikněte na tlačítko **filtru**. Tato možnost může být uveden v horní části úroveň, nebo v podnabídce v části **zarážky**.  
  
### <a name="to-set-a-breakpoint-on-a-specific-computer"></a>Chcete-li nastavit zarážky v určitém počítači  
  
1.  Získání názvu počítače z **procesy** okno.  
  
2.  Vyberte bod přerušení a otevřete **zarážek filtru** dialogové okno jak je popsáno v předchozím postupu.  
  
3.  V **zarážek filtru** dialogové okno, zadejte:  
  
     MachineName =*yourmachinename*  
  
     Chcete-li vytvořit složitější filtr, můžete kombinovat pomocí klauzule `&`, operátor AND `||`, operátor OR `!`, operátor NOT a kulaté závorky.  
  
4.  Click **OK**.  
  
### <a name="to-set-a-breakpoint-on-a-specific-process"></a>Chcete-li nastavit zarážky na specifickém procesu  
  
1.  Získat název procesu nebo zpracovat identifikační číslo z **procesy** okno.  
  
2.  Vyberte bod přerušení a otevřete **zarážek filtru** dialogové jako v prvním postupu.  
  
3.  V **zarážek filtru** dialogové okno, zadejte:  
  
     `ProcessName =`  *yourprocessname*  
  
     —nebo—  
  
     `ProcessID =`*yourprocessIDnumber*  
  
     Chcete-li vytvořit složitější filtr, můžete kombinovat pomocí klauzule `&`, operátor AND `||`, operátor OR `!`, operátor NOT a kulaté závorky.  
  
4.  Click **OK**.  
  
### <a name="to-set-a-breakpoint-on-a-specific-thread"></a>Chcete-li nastavit zarážky konkrétní vlákna  
  
1.  Získání názvu vlákna nebo číslo ID z vlákna **vláken** okno.  
  
2.  Vyberte bod přerušení a otevřete **zarážek filtru** dialogové okno jak je popsáno v prvním postupu.  
  
3.  V **zarážek filtru** dialogové okno, zadejte:  
  
     `ThreadName =`*yourthreadname*  
  
     —nebo—  
  
     `ThreadID =`*yourthreadIDnumber*  
  
     Chcete-li vytvořit složitější filtr, můžete kombinovat pomocí klauzule `&`, operátor AND `||`, operátor OR `!`, operátor NOT a kulaté závorky.  
  
4.  Click **OK**.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak vytvořit filtr pro zarážku na počítači s názvem `marvin` a vlákna s názvem `fourier1`.  
  
```  
(MachineName = marvin) & (ThreadName = fourier1)  
```  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)   
 [Postupy: použití okna procesy](http://msdn.microsoft.com/en-us/0207ce2f-8ceb-4fe7-b2b5-4dd35b035ed7)   
 [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md)   
 [Vláken a procesů](http://msdn.microsoft.com/en-us/73d87480-9af3-4d1b-baf5-397d5d876ae6)   
 [Použití zarážek](../debugger/using-breakpoints.md)