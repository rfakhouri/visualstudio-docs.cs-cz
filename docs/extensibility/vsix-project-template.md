---
title: "Šablona projektu VSIX | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploy packages
- publish extension
ms.assetid: b6c82167-e2a5-4cff-8c8b-2d72e2a9092c
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: de8de116a9853391249a7a37a35bd54d0a6946d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="vsix-project-template"></a>Šablona projektu VSIX
Šablona projektu VSIX slouží k zabalení jedno nebo více rozšíření sady Visual Studio v projektu VSIX a pak publikovat v balíčku [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) webu.  
  
 VSIX nasazení podporuje VSPackages, sestavení, MEF součásti, šablony projektů, šablony položek, ovládací prvky panelu nástrojů a typy vlastní rozšíření.  
  
> [!NOTE]
>  Použití VSIX projektů, je nutné nainstalovat sadu Visual Studio SDK. Další informace o sadě Visual Studio SDK najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="where-to-find-the-vsix-project-template"></a>Kde najít šablona projektu VSIX  
 Šablona projektu VSIX jsou k dispozici v **nový projekt** dialogové okno. Rozbalte položku, buď **jazyka Visual Basic** uzlu nebo **Visual C#** uzel a potom vyberte **rozšiřitelnost**.  
  
> [!TIP]
>  Měli ujistit, že rozhraní .NET Framework 4.5 nebo vyšší je zadána v rozevírací nabídce v horní části **nový projekt** dialogové okno.  
  
## <a name="uses-of-the-vsix-project-template"></a>Používá šablona projektu VSIX  
 Šablona projektu VSIX má dvě hlavní využití:  
  
-   K nasazení šablony projektů, šablony položek a další rozšíření, které již nemají podporu VSIX.  
  
-   Výstupy několik rozšíření zabalit do jednoho nasazení balíčku.  
  
 Nemáte pomocí šablony projektu VSIX nasadit VSPackages nebo jiných druhů rozšíření, které už máte VSIX podporovat.  
  
## <a name="packaging-an-extension-in-an-empty-vsix-project"></a>Balení rozšíření v projektu na prázdný VSIX  
 Můžete balíček existující příponu nebo rozšíření, které již nemá VSIX podporují, a zabalení v prázdný projekt VSIX. Přípona chcete zabalit musí být typu, který je podporován [VSIX schématu](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
#### <a name="to-package-an-extension-by-using-a-vsix-project"></a>Balíček rozšíření pomocí projektu VSIX  
  
1.  Sestavení projektů, které tvoří rozšíření.  
  
2.  Vytvoření projektu VSIX pomocí **projektu VSIX** šablony.  
  
     Source.extension.vsixmanifest se otevře v **Návrhář manifestu**.  
  
3.  Na **prostředky** , zvolte **nový** tlačítko.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
4.  V **typ** seznamu, vyberte typ rozšíření, které chcete přidat.  
  
5.  Pokud chcete přidat element rozšíření nebo obsahu, který je zahrnut v aktuálním řešení (například šablony položky nebo kompilované sestavení), proveďte následující kroky:  
  
    1.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
    2.  V **projektu** seznamu, vyberte název rozšíření.  
  
    3.  V **vložení v této složce** zadejte název složky, do kterého chcete vložit prostředku a potom vyberte **OK** tlačítko.  
  
6.  Pokud chcete přidat rozšíření nebo obsahu elementu, který není zahrnutý v aktuálním řešení, proveďte následující kroky:  
  
    1.  V **zdroj** seznam pole, zvolte **souboru v systému souborů**.  
  
    2.  V **cesta** pole, zadejte úplnou cestu k souboru rozšíření kompilované nebo komprimované nebo použijte **Procházet** tlačítko procházení k souboru.  
  
    3.  V **vložení v této složce** zadejte název složky, do kterého chcete vložit prostředku a potom vyberte **OK** tlačítko.  
  
7.  Pokud chcete, aby váš balíček zahrnout další rozšíření, přidejte je stejným způsobem.  
  
8.  Sestavte řešení.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Vytvoří soubor VSIX, který obsahuje soubor manifestu VSIX, soubor XML [Content_Types] a všechna rozšíření prostředků, které jste přidali do projektu.  
  
## <a name="see-also"></a>Viz také  
 [VSIX rozšíření schéma 2.0 – referenční informace](../extensibility/vsix-extension-schema-2-0-reference.md)   
 [Hledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)