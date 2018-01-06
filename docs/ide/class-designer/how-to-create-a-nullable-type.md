---
title: "Postupy: vytvoření typu s povolenou hodnotou Null (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- nullable types, Class Designer
- Class Designer [Visual Studio], nullable types
ms.assetid: 84673a89-3f6d-4668-919e-1c0f56182fe5
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 17b234a774914e998c228dc780b645864420658d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-nullable-type-class-designer"></a>Postupy: Vytváření typů s povolenou hodnotou Null (návrhář tříd)
Některé typy hodnot vždy nějaké (nebo potřebujete) definovanou hodnotu. Toto je běžnou praxí v databázích, kde některá pole nemusí být přiřazeny žádnou hodnotu. Například můžete do pole databáze do označují, že je ještě nebyly přiřazeny hodnotu přiřadit hodnotu null.  
  
A *typ s možnou hodnotou Null* je typ hodnoty, které rozšířit tak, aby trvá typické rozsahu hodnot pro daný typ a také hodnotu null. Například s možnou hodnotou NULL z `Int32`, také jako s možnou hodnotou Null označují jako\<Int32 >, může být přiřazena libovolná hodnota od -2147483648 2147483647 nebo jej lze přiřadit hodnotu null. Nullable\<bool > je možné přiřadit hodnoty `True`, `False`, nebo hodnota null (žádná hodnota, na všech).  
  
Typy s možnou hodnotou Null jsou instancemi třídy <xref:System.Nullable%601> struktura. Každá instance typu s povolenou hodnotou Null má dvě veřejné vlastnosti jen pro čtení `HasValue` a `Value`:  
  
-   `HasValue`je typu `bool` a určuje, zda proměnná obsahuje hodnotu definované. `True`znamená, že proměnná obsahuje hodnotu než null. Pro hodnotu definovanou můžete otestovat pomocí příkazu `if (x.HasValue)` nebo `if (y != null)`.  
  
-   `Value`je stejného typu jako nadřazený typ. Pokud `HasValue` je `True`, `Value` obsahuje hodnotu smysluplný. Pokud `HasValue` je `False`, přístupu k `Value` vyvolá výjimku neplatná operace.  
  
Ve výchozím nastavení, když deklarovat proměnnou jako typ s možnou hodnotou Null, má žádné definované hodnoty (`HasValue` je `False`), jiné než výchozí hodnotu její základní typ hodnoty.  
  
Návrhář tříd zobrazí typu s povolenou hodnotou Null, stejně jako se zobrazí jeho zdrojovým typem.  
  
Další informace o typech s povolenou hodnotou Null v jazyce Visual C#, najdete v části [typy s možnou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/index). Další informace o typech s povolenou hodnotou Null v jazyce Visual Basic najdete v tématu [typy s možnou hodnotou Null hodnot](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types).  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-add-a-nullable-type-by-using-the-class-designer"></a>Přidejte typ s možnou hodnotou Null pomocí návrháře tříd  
  
1.  V diagramu tříd rozbalit existující třídy nebo vytvořte novou třídu.  
  
2.  Přidat třídu do projektu na **diagramu tříd** nabídky, klikněte na tlačítko **přidat**a potom klikněte na **přidat třídu**.  
  
3.  Na rozšíření třídy tvaru, **diagramu tříd** nabídky, klikněte na tlačítko **rozbalte**.  
  
4.  Vyberte třídu tvaru. Na **diagramu tříd** nabídky, klikněte na tlačítko **přidat**a potom klikněte na **pole**. Nové pole, která má výchozí název **pole** se zobrazí ve tvaru třídy a taky ve **podrobností třídy** okno.  
  
5.  V **název** sloupec **podrobností třídy** okno (nebo ve třídě utvářejí sám sebe), změňte název nového pole na platný a smysluplný název.  
  
6.  V **typ** sloupec **podrobností třídy** okně deklarovat typ jako typ s možnou hodnotou Null, jak je znázorněno v následujícím kódu:  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
### <a name="to-add-a-nullable-type-by-using-the-code-editor"></a>Přidejte typ s možnou hodnotou Null pomocí editoru kódu  
  
1.  Přidejte třídu do projektu. Vyberte uzel projektu v **Průzkumníku řešení**a na **projektu** nabídky, klikněte na tlačítko **přidat třídu**.  
  
2.  V souboru cs nebo VB nové třídy přidejte jeden nebo více typů s povolenou hodnotou Null novou třídu do deklaraci třídy.  
  
3.  Ze třídy zobrazení přetáhněte novou ikonu třídy na návrhovou plochu návrhář tříd. Třída obrazce se zobrazí v diagramu tříd.  
  
4.  Rozbalte Podrobnosti obrazce Třída a přesuňte ukazatel myši nad členy třídy. Popisek zobrazí deklaraci každého člena.  
  
5.  Klikněte pravým tlačítkem na tvar třídu a klikněte na tlačítko **podrobností třídy**. Můžete zobrazit nebo upravit vlastnosti nového typu v **podrobností třídy** okno.  
  
## <a name="see-alose"></a>V tématu alose
<xref:System.Nullable%601>   
[Typy s možnou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/index)   
[Použití typů s povolenou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/using-nullable-types)   
[Postupy: identifikace typu s povolenou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type)   
[Typy hodnot s povolenou hodnotou Null](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)