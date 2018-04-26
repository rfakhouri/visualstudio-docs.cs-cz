---
title: Dialogové okno Požadavky
ms.date: 01/18/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.Bootstrapper
helpviewer_keywords:
- Prerequisites dialog box
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 37400624d81c533e6ecddb9d6278b5b372410525
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="prerequisites-dialog-box"></a>Dialogové okno Požadavky

Toto dialogové okno určuje požadovaných součástí, které jsou nainstalovány, způsobu instalace a které pořadí, jestli že jsou nainstalované balíčky.

Pro přístup k tohoto dialogového okna, vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **publikovat** kartě. Na **publikovat** klikněte na tlačítko **požadavky**. Pro projekty instalace na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **stránky vlastností** se zobrazí dialogové okno, klikněte na tlačítko **požadavky**.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

|Prvek|Popis|
|-------------|-----------------|
|**Vytvořit instalační program pro instalaci požadovaných součástí**|Obsahuje součásti, které ve vaší aplikaci instalačního programu (Setup.exe) tak, aby se nainstalují před vaší aplikace, v pořadí podle závislostí. Ve výchozím nastavení je tato možnost vybrána. Pokud není zaškrtnuto, vytvoří se žádné Setup.exe.|
|**Vyberte, které požadavky pro instalaci**|Určuje, zda chcete nainstalovat komponenty, jako [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)], Crystal Reports a tak dále.<br /><br /> Například podle zaškrtněte políčko vedle **SQL Server 2005 Express Edition SP2**, určíte, že instalační program ověřte, jestli tato součást je nainstalován v cílovém počítači a nainstalujte ji, pokud již není nainstalována.<br /><br /> Podrobné informace o jednotlivých požadovaných součástí balíčku najdete v tabulce informací o požadavcích později v tomto tématu.|
|**Kontrolovat více distribuovatelné součásti Microsoft Update**|Kliknutím na tento odkaz přejdete na [balíčků zaváděcího nástroje znovu distribuovat součástí](http://go.microsoft.com/fwlink/?LinkId=208835) webu ke kontrole aktualizací.|
|**Stažení požadované součásti z webu dodavatele součásti**|Určuje, že požadované součásti nainstalovat z webu dodavatele. Toto je výchozí možnost.|
|**Stáhnout požadavky ze stejného umístění jako Moje aplikace**|Určuje, že požadované součásti nainstalovat ze stejného umístění jako aplikace. Zkopíruje všechny požadované balíčky do umístění pro publikování. Tato možnost bude fungovat, pouze pokud jsou balíčky požadovaných součástí ve vývojovém počítači.|
|**Stažení požadované součásti z následujícího umístění**|Určuje, že požadované součásti nainstalovat z umístění, které vyberete. Můžete použít **Procházet** tlačítko vyberte umístění.|

## <a name="prerequisites-information"></a>Informací o požadavcích

Požadované součásti, které se zobrazují v **požadavky** dialogové okno mohou lišit od těch v následujícím seznamu. Požadované balíčky uvedené v **dialogové okno požadavky** jsou automaticky nastavit poprvé otevřete dialogové okno. Pokud později změníte cílový framework projektu na, je nutné vybrat požadavky ručně tak, aby odpovídala nové cílové rozhraní.

|Prvek|Popis|
|-------------|-----------------|
|**Rozhraní .NET framework 3.5 SP1**|Tento balíček nainstaluje následující:<br /><br /> -Rozhraní .NET framework verze 2.0, 3.0 a 3.5.<br />-Podpora pro všechny verze rozhraní .NET Framework na 32bitové (x86) a (x64) 64bitové operační systémy.<br />-Jazykové sady pro každou verzi rozhraní .NET Framework, která se instaluje se balíček.<br />-Služba sady pro rozhraní .NET Framework 2.0 a 3.0.<br /><br /> Rozhraní .NET framework 3.0 je součástí systému Windows Vista a rozhraní .NET Framework 3.5 je součástí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Rozhraní .NET framework 3.5 je vyžadována pro všechny projekty Visual Basic a C#, kompilovaná pro 32bitové operační systémy a pro který cílovém Frameworku, který je nastaven na **rozhraní .NET Framework 3.5**a pro projekty Visual Basic a C# zkompilovat pro 64bitové prostředí operační systémy. (IA64 není podporována.) Všimněte si, že jsou projekty Visual Basic a C# zkompilovaném pro všechny architektura procesoru ve výchozím nastavení. Další informace najdete v tématu [přehled cílení na více Visual Studio](../../ide/visual-studio-multi-targeting-overview.md) a [nasazení požadovaných součástí pro 64bitové aplikace](../../deployment/deploying-prerequisites-for-64-bit-applications.md).<br /><br /> Ve výchozím nastavení je vybraná tato položka.|
|**Rozhraní Microsoft .NET Framework 4.x**|Tento balíček nainstaluje rozhraní .NET Framework 4.x pro x86 a x64 platformy.|
|**Microsoft System CLR Types pro SQL Server 2014 (x64 a x86)**|Tento balíček nainstaluje Microsoft System CLR Types pro SQL Server 2014 pro x64 nebo x86.|
|**SQL Server 2008 R2 Express**|Tento balíček nainstaluje Microsoft SQL Server 2008 R2 Express, bezplatná edice systému Microsoft SQL Server 2008 R2, databázi ideální pro malé webové, server nebo aplikací klasické pracovní plochy. Může sloužit zdarma pro vývoj a produkci.|
|**SQL Server 2012 Express**|Tento balíček nainstaluje Microsoft SQL Server 2012 Express.|
|**SQL Server 2012 Express LocalDB**|Tento balíček nainstaluje Microsoft SQL Server 2012 Express LocalDB.|
|**"14" Runtime knihoven Visual C++ (ARM)**|Tento balíček nainstaluje běhové knihovny jazyka Visual C++ pro architekturu Itanium, které poskytují rutiny pro programování pro operační systém Microsoft Windows. Tyto rutiny automatizovat mnoho běžných programovacích úloh, které nejsou k dispozici jazyky C a C++.<br /><br /> Další informace najdete v tématu [referenční dokumentace knihoven C Run-Time](/cpp/c-runtime-library/c-run-time-library-reference).|
|**Knihovny jazyka Visual C++ Runtime "14" (x64)**|Tento balíček nainstaluje běhové knihovny jazyka Visual C++ pro x64 operační systémy, které poskytují rutiny pro programování pro operační systém Microsoft Windows. Tyto rutiny automatizovat mnoho běžných programovacích úloh, které nejsou k dispozici jazyky C a C++.<br /><br /> Další informace najdete v tématu [referenční dokumentace knihoven C Run-Time](/cpp/c-runtime-library/c-run-time-library-reference).|
|**Knihovny jazyka Visual C++ Runtime "14" (x86)**|Tento balíček nainstaluje běhové knihovny jazyka Visual C++ pro x86 operační systémy, které poskytují rutiny pro programování pro operační systém Microsoft Windows. Tyto rutiny automatizovat mnoho běžných programovacích úloh, které nejsou k dispozici jazyky C a C++.<br /><br /> Další informace najdete v tématu [referenční dokumentace knihoven C Run-Time](/cpp/c-runtime-library/c-run-time-library-reference).|

## <a name="see-also"></a>Viz také

- [Stránka Publikovat, Návrhář projektu](../../ide/reference/publish-page-project-designer.md)
- [Nezbytné součásti nasazení aplikace](../../deployment/application-deployment-prerequisites.md)
- [Nasazení nezbytných součástí pro 64bitové aplikace](../../deployment/deploying-prerequisites-for-64-bit-applications.md)
- [Přehled cílení na více verzí sady Visual Studio](../../ide/visual-studio-multi-targeting-overview.md)
