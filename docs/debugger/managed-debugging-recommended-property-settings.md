---
title: "Spravované ladění: Doporučené nastavení vlastností | Microsoft Docs"
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
- debugging [Visual Studio], managed
- debugging managed code, recommended property settings
ms.assetid: 3d14a8d4-2925-44d0-be41-ec546d411db9
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f763decca7a80a7a7fc5bb86f94a76cd3eb2679c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managed-debugging-recommended-property-settings"></a>Spravované ladění: doporučené nastavení vlastností
Některé vlastnosti musí být nastaven stejným způsobem jako pro všechny spravované ladění scénáře.  
  
 Následující tabulky obsahují doporučené nastavení vlastností.  
  
 Mezi typy jiný spravovaný projekt se mohou lišit nastavení, které zde nejsou uvedeny. Například **spustit akci** bude nastavena jinak v projektu Windows Forms než [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] projektu.  
  
### <a name="configuration-properties-on-the-build-c-or-compile-visual-basic-tab"></a>Vlastnosti konfigurace na kartě sestavení (C#) nebo kompilace (Visual Basic)  
  
|**Název vlastnosti**|**Nastavení**|  
|-----------------------|-----------------|  
|**Definování ladění konstanta**|C# a F #: nastavte políčko zaškrtnuté. To umožňuje vaší aplikace pro použití třídy ladění.|  
|**Definování trasování konstanta**|C# a F #: nastavte políčko zaškrtnuté. To umožňuje vaší aplikaci používat třídu trasování.|  
|**Optimalizace kódu**|C#, F # a Visual Basic: nastavte na hodnotu false. Optimalizovaný kód je těžší ladit, protože vygenerovaný pokyny neodpovídají přímo ke zdrojovému kódu. Pokud zjistíte chybu, která se zobrazí pouze v optimalizovaný kód má program, můžete zapnout toto nastavení, ale mějte na paměti, tento kód ukazuje **zpětný překlad** okno se generují z optimalizované zdroj, který se nemusí shodovat s co vidíte v kódu Editor. K ladění optimalizovaného kódu, je nutné vypnout pouze můj kód. (Viz [omezit zanoříte se pouze můj kód](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Restrict_stepping_to_Just_My_Code)).<br /><br /> Další informace najdete v tématu [nastavení projektu pro ladění konfigurace C#](../debugger/project-settings-for-csharp-debug-configurations.md) nebo [nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).|  
|**Výstupní cesta**|Nastavte na bin\Debug\\.|  
|**Možnosti rozšířené kompilace**|Pouze v jazyce Visual Basic. Klikněte na tlačítko **Upřesnit** nastavit rozšířené vlastnosti, které jsou popsané v následující tabulce.|  
  
### <a name="advanced-compiler-settings-dialog-box"></a>dialogové okno Upřesnit nastavení kompilátoru  
  
|**Název vlastnosti**|**Nastavení**|  
|-----------------------|-----------------|  
|**Povolit optimalizace**|Z důvodů uvedených v nastavena na hodnotu false **optimalizace kódu** možnost v předchozí tabulce.|  
|**Generovat ladicí informace**|Výběrem tohoto zaškrtávacího políčka způsobí příznak/Debug nastavit, když kompilujete, který bude generovat informace potřebné k usnadnění ladění.|  
|**Definování ladění konstanta**|Toto políčko zaškrtněte, chcete-li definovat `DEBUG` konstanta, která umožňuje aplikace pomocí <xref:System.Diagnostics.Debug> třídy.|  
|**Definování trasování konstanta**|Toto políčko zaškrtněte, chcete-li definovat `TRACE` konstanta, která umožňuje aplikace pomocí <xref:System.Diagnostics.Trace> třídy.|  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)