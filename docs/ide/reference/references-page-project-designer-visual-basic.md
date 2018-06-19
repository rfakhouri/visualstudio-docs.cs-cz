---
title: Stránka Odkazy, návrhář projektu (Visual Basic)
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesReference
- vb.ProjectPropertiesUnusedReference
- vb.ProjectPropertiesReferencePaths
helpviewer_keywords:
- References page in Project Designer
- Project Designer, References page
- Unused References dialog box
ms.assetid: 5a47c595-e084-401c-86e1-74e0bf74fd86
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 35534c0c6965dd7f7db01e2299ff71572b8de9e7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31950290"
---
# <a name="references-page-project-designer-visual-basic"></a>Stránka Odkazy, návrhář projektu (Visual Basic)
Použití **odkazy** stránky **Návrhář projektu** ke správě odkazy, webové odkazy a importovaných oborů názvů ve vašem projektu. Projekty mohou obsahovat odkazy na komponenty modelu COM, webové služby XML, knihovny tříd rozhraní .NET Framework nebo sestavení nebo jiné knihovny tříd. Další informace o použití odkazy, najdete v části [Správa odkazů v projektu](../../ide/managing-references-in-a-project.md).

 Pro přístup k **odkazy** vyberte uzel projektu (ne **řešení** uzel) v **Průzkumníku řešení**. Zvolte **projektu**, **vlastnosti** v řádku nabídek. Jakmile se zobrazí v Návrháři projektu, klikněte na tlačítko **odkazy** kartě.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 Následující možnosti vám umožňují vyberte nebo odebrání odkazů a importovaných oborů názvů ve vašem projektu.

 **Nepoužívané odkazy**

 Kliknutím na toto tlačítko přístup **nepoužívané odkazy** dialogové okno.

 **Nepoužívané odkazy** dialogové okno umožňuje odebrat odkazy, které jsou součástí projektu, ale ve skutečnosti není používána kód. Obsahuje tabulku, ve které jsou uvedené **název odkazu**, **cesta**a další informace o odkazy na obor názvů nepoužívané ve vašem projektu. V mřížce, vyberte odkazy na obor názvů, které chcete odebrat z projektu a klikněte na **odebrat**.

 **Odkaz na cesty**

 Kliknutím na toto tlačítko přístup **cesty odkazů** dialogové okno.

> [!NOTE]
> Když systém projektu vyhledá odkaz na sestavení, systému vyřeší odkaz tak, že vyhledá v následujících umístěních, v uvedeném pořadí:

>
>  1.  Složce projektu. Soubory složce projektu se zobrazí v **Průzkumníku řešení** při **zobrazit všechny soubory** se neuplatní.
> 2.  Složky, které jsou určené v **cesty odkazů** dialogové okno.
> 3.  Složky, které soubory v zobrazení **přidat odkaz na** dialogové okno.
> 4.  Složce obj. projektu. (Když přidáte do projektu odkaz modelu COM, jeden nebo více sestavení může být přidány do projektu složce obj..)

 **Odkazy**

 Tento seznam obsahuje všechny odkazy v projektu používá nebo se nepoužívá.

 **Přidat**

 Kliknutím na Přidat odkaz nebo webový odkaz na toto tlačítko **odkazy** seznamu.

 Zvolte **odkaz** se přidat odkaz na projekt pomocí dialogového okna Přidat odkaz.

 Zvolte **webový odkaz** přidat odkaz na projekt pomocí dialogového okna Přidat odkaz na Web.

 **Odebrat**

 Vyberte jeden nebo více odkazů v **odkazy** seznamu a pak klikněte na toto tlačítko Odstranit.

 **Aktualizovat webový odkaz**

 Vyberte webový odkaz v **odkazy** seznamu a kliknutím na toto tlačítko Aktualizovat.

 **Importované obory názvů**

 Můžete zadat vlastní obor názvů v tomto poli a klikněte na tlačítko **přidat Import uživatelů** ho přidejte do seznamu oborů názvů.

 Můžete vytvořit aliasy pro uživatele importované obory názvů. Chcete-li to provést, zadejte ve formátu alias a obor názvů *alias*=*obor názvů*. To je užitečné, pokud používáte dlouho obory názvů, například: `Http= MyOrg.ObjectLib.Internet.WebRequestMethods.Http`.

 **Přidat Import uživatelů**

 Kliknutím na toto tlačítko Přidat obor názvů specifikovaný v **importovat obory názvů** pole v seznamu importovaných oborů názvů. Tlačítko je aktivní jenom v případě, že zadaný obor názvů již není v seznamu.

 **Seznam obory názvů**

 Tento seznam obsahuje všechny dostupných oborů názvů. Zaškrtnuto políčko pro obory názvů zahrnuté ve vašem projektu.

 **Import uživatelů aktualizace**

 Vyberte obor názvů definované uživatelem v seznamu obory názvů, zadejte název, který chcete nahradit její v **importovat obory názvů** pole a pak klikněte na toto tlačítko Změnit na nový obor názvů. Tlačítko je aktivní jenom v případě, že vybraný obor názvů je ten, který jste přidali do seznamu pomocí **přidat Import uživatelů** tlačítko. Můžete přidat:

-   Třídy nebo obory názvů, jako například <xref:System.Math?displayProperty=fullName>.

-   Alias importuje, jako například `VB=Microsoft.VisualBasic`.

-   Obory názvů XML, jako například `<xmlns:xsl="http://www.w3.org/1999/XSL/Transform">`.

## <a name="see-also"></a>Viz také

- [Správa odkazů v projektu](../../ide/managing-references-in-a-project.md)
- [Postupy: Přidání nebo odebrání importovaných oborů názvů (Visual Basic)](../../ide/how-to-add-or-remove-imported-namespaces-visual-basic.md)
- [Příkaz Imports (obor názvů XML)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)
