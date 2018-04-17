---
title: 'Postupy: vytváření přidružení souborů pro aplikaci ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 75215164de3aedfe1ea0168275280304dfd5def9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>Postupy: Vytváření přidružení souborů pro aplikaci ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace může být přidružený jeden nebo více přípon souborů, takže aplikace se spustila automaticky, když uživatel otevře soubor z těchto typů. Přidání podpory přípony názvu souboru [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace je jednoduché.  
  
### <a name="to-create-file-associations-for-a-clickonce-application"></a>Vytvořit přidružení pro aplikaci ClickOnce  
  
1.  Vytvoření [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace za normálních okolností nebo použít stávající [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
2.  S textem nebo editoru XML, jako je například Poznámkový blok otevřete manifest aplikace.  
  
3.  Najít `assembly` elementu. Další informace najdete v tématu [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md).  
  
4.  Jako podřízenou `assembly` elementu, přidejte `fileAssociation` elementu. `fileAssociation` Element má čtyři atributy:  
  
    -   `extension`: Příponu názvu souboru, který chcete přidružit k aplikaci.  
  
    -   `description`: Popis typu souboru, který se zobrazí v prostředí systému Windows.  
  
    -   `progid`: Řetězec jednoznačně určující typ souboru, k označení v registru.  
  
    -   `defaultIcon`: Ikonu pro tento typ souboru. Ikona je nutné přidat jako prostředek souborů v manifestu aplikace. Další informace najdete v tématu [postupy: zahrnutí datového souboru v aplikaci ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
     Příklad `file` a `fileAssociation` elementy, najdete v části [ \<fileAssociation > Element](../deployment/fileassociation-element-clickonce-application.md).  
  
5.  Pokud chcete k aplikaci přidružit více než jeden typ souboru, přidejte další `fileAssociation` elementy. Všimněte si, že `progid` atributu by měla být různé pro jednotlivé.  
  
6.  Po dokončení s manifest aplikace znovu podepište manifest. Můžete to provést z příkazového řádku pomocí Mage.exe.  
  
     `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
     Další informace najdete v tématu [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)  
  
## <a name="see-also"></a>Viz také  
 [\<fileAssociation > elementu](../deployment/fileassociation-element-clickonce-application.md)   
 [ClickOnce – Manifest aplikace](../deployment/clickonce-application-manifest.md)   
 [Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)