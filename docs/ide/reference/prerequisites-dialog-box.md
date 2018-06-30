---
title: Dialogové okno Požadavky
ms.date: 06/29/2018
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
ms.openlocfilehash: a1360b63eb1469efe4948f2859e28a567b00ad1a
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117261"
---
# <a name="prerequisites-dialog-box"></a>dialogové okno Požadavky

**Požadavky** dialogové okno určuje požadovaných součástí, které jsou nainstalovány, způsobu instalace a které pořadí, jsou nainstalované balíčky.

![V sadě Visual Studio dialogové okno požadavky](media/prerequisites-dialog-box.png)

Pro přístup k dialogu, vyberte uzel projektu v **Průzkumníku řešení**a potom vyberte **projektu** > **vlastnosti**. Když **Návrhář projektu** se zobrazí, vyberte **publikovat** a pak vyberte **požadavky**. Pro projekty instalace na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **stránky vlastností** se zobrazí dialogové okno, klikněte na tlačítko **požadavky**.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

|Prvek|Popis|
|-------------|-----------------|
|**Vytvořit instalační program pro instalaci požadovaných součástí**|Obsahuje součásti, které vaše aplikace instalačního programu (*Setup.exe*), aby se jejich budete nainstalovat před vaší aplikace, v pořadí podle závislostí. Ve výchozím nastavení je tato možnost vybrána. Pokud není zaškrtnuto, žádné *Setup.exe* je vytvořena.|
|**Vyberte, které požadavky pro instalaci**|Určuje, jestli chcete-li nainstalovat komponenty, například rozhraní .NET Framework a C++ runtime knihoven.<br /><br />Například podle zaškrtněte políčko vedle **SQL Server 2012 Express**, určíte, že instalační program musí ověřte, jestli tato součást je nainstalován v cílovém počítači a nainstalujte ji, pokud není.<br /><br />Podrobné informace o jednotlivých požadovaných součástí balíčku najdete v tématu [informací o požadavcích](#prerequisites-information).|
|**Stažení požadované součásti z webu dodavatele součásti**|Určuje, že požadované součásti nainstalovat z webu dodavatele. Toto je výchozí možnost.|
|**Stáhnout požadavky ze stejného umístění jako Moje aplikace**|Určuje, že požadované součásti nainstalovat ze stejného umístění jako aplikace. Zkopíruje všechny požadované balíčky do umístění pro publikování. Tato možnost bude fungovat, pouze pokud jsou balíčky požadovaných součástí ve vývojovém počítači.|
|**Stažení požadované součásti z následujícího umístění**|Určuje, že požadované součásti nainstalovat z umístění, které zadáte. Můžete použít **Procházet** tlačítko vyberte umístění.|

## <a name="prerequisites-information"></a>Informací o požadavcích

Požadované součásti, které se zobrazují v **požadavky** dialogové okno mohou lišit od těch v následujícím seznamu. Požadované balíčky uvedené v **dialogové okno požadavky** jsou automaticky nastavit poprvé otevřete dialogové okno. Pokud později změníte cílový framework projektu na, musíte vybrat požadavky ručně tak, aby odpovídala nové cílové rozhraní.

|Prvek|Popis|
|-------------|-----------------|
|**Rozhraní .NET framework 3.5 SP1**|Tento balíček nainstaluje následující:<br /><br /> -Rozhraní .NET framework verze 2.0, 3.0 a 3.5.<br />-Podpora pro všechny verze rozhraní .NET Framework na 32bitové (x86) a (x64) 64bitové operační systémy.<br />-Jazykové sady pro každou verzi rozhraní .NET Framework, která se instaluje se balíček.<br />-Služba sady pro rozhraní .NET Framework 2.0 a 3.0.<br /><br /> Rozhraní .NET framework 3.0 je součástí systému Windows Vista a rozhraní .NET Framework 3.5 je obsažen v sadě Visual Studio. Rozhraní .NET framework 3.5 je vyžadována pro všechny projekty Visual Basic a C#, kompilovaná pro 32bitové operační systémy a pro který cílovém Frameworku, který je nastaven na **rozhraní .NET Framework 3.5**a pro projekty Visual Basic a C# zkompilovat pro 64bitové prostředí operační systémy. (IA64 není podporována.) Všimněte si, že jsou projekty Visual Basic a C# zkompilovaném pro všechny architektura procesoru ve výchozím nastavení. Další informace najdete v tématu [přehled cílení na více Visual Studio](../../ide/visual-studio-multi-targeting-overview.md) a [nasazení požadovaných součástí pro 64bitové aplikace](../../deployment/deploying-prerequisites-for-64-bit-applications.md).|
|**Rozhraní Microsoft .NET Framework 4.x**|Tento balíček nainstaluje rozhraní .NET Framework 4.x pro x86 a x64 platformy.|
|**Microsoft System CLR Types pro SQL Server 2014 (x64 a x86)**|Tento balíček nainstaluje Microsoft System CLR Types pro SQL Server 2014 pro x64 nebo x86.|
|**SQL Server 2008 R2 Express**|Tento balíček nainstaluje Microsoft SQL Server 2008 R2 Express, bezplatná edice systému Microsoft SQL Server 2008 R2, databázi ideální pro malé webové, server nebo aplikací klasické pracovní plochy. Může sloužit zdarma pro vývoj a produkci.|
|**SQL Server 2012 Express**|Tento balíček nainstaluje Microsoft SQL Server 2012 Express.|
|**SQL Server 2012 Express LocalDB**|Tento balíček nainstaluje Microsoft SQL Server 2012 Express LocalDB.|
|**"14" Runtime knihoven Visual C++ (ARM)**|Tento balíček nainstaluje běhové knihovny jazyka Visual C++ pro architekturu Itanium, které poskytují rutiny pro programování pro operační systém Microsoft Windows. Tyto rutiny automatizovat mnoho běžných programovacích úloh, které nejsou k dispozici jazyky C a C++.<br /><br /> Další informace najdete v tématu [referenční dokumentace knihoven C Run-Time](/cpp/c-runtime-library/c-run-time-library-reference).|
|**Knihovny jazyka Visual C++ Runtime "14" (x64)**|Tento balíček nainstaluje běhové knihovny jazyka Visual C++ pro x64 operační systémy, které poskytují rutiny pro programování pro operační systém Microsoft Windows. Tyto rutiny automatizovat mnoho běžných programovacích úloh, které nejsou k dispozici jazyky C a C++.<br /><br /> Další informace najdete v tématu [referenční dokumentace knihoven C Run-Time](/cpp/c-runtime-library/c-run-time-library-reference).|
|**Knihovny jazyka Visual C++ Runtime "14" (x86)**|Tento balíček nainstaluje běhové knihovny jazyka Visual C++ pro x86 operační systémy, které poskytují rutiny pro programování pro operační systém Microsoft Windows. Tyto rutiny automatizovat mnoho běžných programovacích úloh, které nejsou k dispozici jazyky C a C++.<br /><br /> Další informace najdete v tématu [referenční dokumentace knihoven C Run-Time](/cpp/c-runtime-library/c-run-time-library-reference).|

## <a name="see-also"></a>Viz také:

- [Stránka Publikovat, Návrhář projektu](../../ide/reference/publish-page-project-designer.md)
- [Nezbytné součásti nasazení aplikace](../../deployment/application-deployment-prerequisites.md)
- [Nasazení nezbytných součástí pro 64bitové aplikace](../../deployment/deploying-prerequisites-for-64-bit-applications.md)
- [Přehled cílení na více verzí sady Visual Studio](../../ide/visual-studio-multi-targeting-overview.md)