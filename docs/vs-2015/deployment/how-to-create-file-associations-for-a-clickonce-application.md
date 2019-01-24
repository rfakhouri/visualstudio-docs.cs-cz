---
title: 'Postupy: Vytváření přidružení souborů pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 42c7a65625d8e21ceff1070ccbc66d5881af853d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54790949"
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>Postupy: Vytváření přidružení souborů pro aplikaci ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace může být přidružený jeden nebo více přípon souborů, tak, aby aplikaci spustit automaticky, když uživatel otevře soubor z těchto typů. Přidání podpory přípony názvu souboru [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikací je jednoduché.  
  
### <a name="to-create-file-associations-for-a-clickonce-application"></a>Chcete-li vytvořit přidružení souborů pro aplikaci ClickOnce  
  
1. Vytvoření [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace za normálních okolností nebo použít stávající [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace.  
  
2. Otevření manifestu aplikace se textovém editoru nebo editoru XML, jako je například Poznámkový blok.  
  
3. Najít `assembly` elementu. Další informace najdete v tématu [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md).  
  
4. Jako podřízený objekt `assembly` element, přidejte `fileAssociation` elementu. `fileAssociation` Element má čtyři atributy:  
  
   - `extension`: Přípona názvu souboru, kterou chcete přiřadit k aplikaci.  
  
   - `description`: Popis typu souboru, který se zobrazí v prostředí Windows.  
  
   - `progid`: Řetězec, který jednoznačně identifikuje typ souboru k označení v registru.  
  
   - `defaultIcon`: Ikona pro tento typ souboru. Ikona je nutné přidat jako soubor prostředků v manifestu aplikace. Další informace najdete v tématu [jak: Zahrnutí datového souboru do aplikace ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
     Příkladem `file` a `fileAssociation` prvky, naleznete v tématu [ \<fileAssociation > Element](../deployment/fileassociation-element-clickonce-application.md).  
  
5. Pokud chcete přidružit více než jeden typ souboru aplikace, přidejte další `fileAssociation` elementy. Všimněte si, `progid` atribut by měl být různé pro jednotlivé.  
  
6. Jakmile budete hotovi s manifestem aplikace, znovu podepište manifest. Můžete to provést z příkazového řádku s použitím Mage.exe.  
  
    `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
    Další informace najdete v tématu [Mage.exe (Manifest Generation and Editing Tool)](http://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)  
  
## <a name="see-also"></a>Viz také  
 [\<fileAssociation> Element](../deployment/fileassociation-element-clickonce-application.md)   
 [ClickOnce – Manifest aplikace](../deployment/clickonce-application-manifest.md)   
 [Mage.exe (Manifest Generation and Editing Tool)](http://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)
