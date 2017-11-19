---
title: "Příprava rozšíření pro nasazení Instalační služby systému Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: vsix msi
ms.assetid: 5ee2d1ba-478a-4cb7-898f-c3b4b2ee834e
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6d9568cd6fd26683e035ed9889e0d0b7928ce799
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="preparing-extensions-for-windows-installer-deployment"></a>Příprava rozšíření pro nasazení Instalační služby systému Windows
K instalaci balíčku VSIX nelze použít balíček Instalační služby systému Windows (MSI). Však můžete rozbalit obsah balíčku VSIX pro nasazení MSI. Tento dokument ukazuje, jak připravit na projekt, jejíž výchozí výstup je balíčku VSIX pro zahrnutí do projektu instalace.  
  
## <a name="preparing-an-extension-project-for-windows-installer-deployment"></a>Příprava projektu rozšíření pro nasazení Instalační služby systému Windows  
 Proveďte tyto kroky na nové projekty rozšíření před přidáním do projektu instalace.  
  
#### <a name="to-prepare-an-extension-project-for-windows-installer-deployment"></a>Při přípravě rozšíření projektu nasazení Instalační služby systému Windows  
  
1.  Vytvořte VSPackage, MEF komponenty, dalších úprav editoru nebo jiné rozšíření projektu typu, který obsahuje VSIX manifest.  
  
2.  VSIX manifest otevřete v editoru kódu.  
  
3.  Nastavit InstalledByMsi prvku manifestu VSIX, aby `true`. Další informace o VSIX manifestu najdete v tématu [referenční informace o VSIX rozšíření schématu 2.0](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
     To brání tomu, aby instalační program VSIX pokusu o instalaci součásti.  
  
4.  Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a klikněte na tlačítko **vlastnosti**.  
  
5.  Vyberte **VSIX** kartě.  
  
6.  Zaškrtněte políčko s názvem bez přípony **VSIX kopírovat obsah do následujícího umístění** a zadejte cestu, do které projekt instalace vyzvedne, až bude soubory.  
  
## <a name="extracting-files-from-an-existing-vsix-package"></a>Extrahování souborů z existujícího balíčku VSIX  
 Proveďte tyto kroky přidání obsahu existujícího balíčku VSIX do projektu instalace, když nemáte zdrojové soubory.  
  
#### <a name="to-extract-files-from-an-existing-vsix-package"></a>Extrahujte soubory z existujícího balíčku VSIX  
  
1.  Přejmenujte. VSIX obsahující rozšíření z *filename*VSIX k *filename*.zip.  
  
2.  Zkopírujte obsah souboru ZIP do adresáře.  
  
3.  Odstraňte soubor .xml [Content_types] z adresáře.  
  
4.  Upravte VSIX manifest, jak je znázorněno v předchozím postupu.  
  
5.  Přidejte do projektu instalace zbývající soubory.  
  
## <a name="see-also"></a>Viz také  
 [Nasazení instalačního programu sady Visual Studio](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Návod: Vytvoření vlastní akce](http://msdn.microsoft.com/en-us/4bd4b63a-2b91-431e-839c-5752443f0eaf)