---
title: Knihovna webových prvků (spravovaný kód) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], Web control libraries
ms.assetid: 2413883f-9e88-406d-b874-0ed743b75d40
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 17be48435dd8251d1269c7a95195d794f750d534
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797344"
---
# <a name="web-control-library-managed-code"></a>Knihovna webových prvků (spravovaný kód)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Šablona projektu knihovny ovládacích prvků webové vytvoří knihovnu DLL. Vzhledem k tomu, že knihovna tříd je knihovna DLL, nelze ji spustit přímo. Je nutné vytvořit [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] stránka, která vloží ovládací prvek. Další informace najdete v tématu [šablony ovládacího prvku knihovny](http://msdn.microsoft.com/00666b07-71d2-4ace-a13c-cc130a3ce372).  
  
### <a name="to-debug-a-web-control-library-method-1"></a>Chcete-li ladit Knihovna webových prvků (metoda 1)  
  
1.  Otevřete existující projekt Knihovna ovládacích prvků webového, nebo vytvořte novou.  
  
2.  Vytvoření [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] stránka, která vloží ovládací prvek.  
  
3.  Na webu, který je hostitelem [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] program test harness, vytvořte podadresář s názvem `/Code`.  
  
4.  Zkopírujte zdrojový kód do ovládacího prvku `/Code` podadresáře.  
  
5.  Otevřete zdrojový kód v `/Code` podadresář nastavování zarážek.  
  
6.  Otevřete okno prohlížeče s adresou URL, která odkazuje na testovací prostředí. V ovládacím prvku bude dosaženo zarážkou a ladění lze spustit.  
  
### <a name="to-debug-a-web-control-library-method-2"></a>Chcete-li ladit Knihovna webových prvků (metoda 2)  
  
1.  Vytvoření projektu hostitelské aplikace a ovládací prvek webového projektu ve stejném řešení.  
  
2.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na hostitele aplikace a zvolte **přidat odkaz**.  
  
3.  Přidáte odkaz do webového projektu ovládacího prvku.  
  
## <a name="see-also"></a>Viz také  
 [ASP.NET – webové aplikace](../debugger/debugging-preparation-aspnet-web-applications.md)
