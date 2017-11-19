---
title: "Postupy: zahrnutí datového souboru v aplikaci ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, data
- deploying applications [ClickOnce], data files
- data access, ClickOnce applications
ms.assetid: 89ee46ef-bc8c-4ab0-a2ac-1220f9da06fc
caps.latest.revision: "15"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: b03083ce6e9fe7fcebdad0b82373bee41221bbb5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-include-a-data-file-in-a-clickonce-application"></a>Postupy: Zahrnutí datového souboru do aplikace ClickOnce
Každý [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] instalací aplikací je přiřazen adresář na místní disk cílového počítače, kde aplikace může spravovat svá vlastní data. Datové soubory mohou zahrnovat souborů všech typů: textové soubory, soubory XML nebo i soubory databáze (.mdb) Microsoft Access. Následující postupy ukazují, jak přidat datový soubor libovolného typu do vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
### <a name="to-include-a-data-file-by-using-mageexe"></a>Chcete-li zahrnout datový soubor pomocí Mage.exe  
  
1.  Přidáte datový soubor do adresáře aplikace s ostatními soubory aplikace.  
  
     Obvykle adresáře aplikace bude adresář s názvem bez přípony s aktuální verzí nasazení – například v1.0.0.0.  
  
2.  Aktualizujte manifest aplikace do seznamu datového souboru.  
  
     **Mage -u v1.0.0.0\Application.manifest - FromDirectory v1.0.0.0**  
  
     Jak tento úkol provést znovu vytvoří seznam souborů v manifestu aplikace a také automaticky vygeneruje podpisy hodnoty hash.  
  
3.  Otevřete manifest aplikace v upřednostňovaném textovém editoru nebo editoru XML a najděte `file` element nedávno přidaného souboru.  
  
     Pokud jste přidali soubor XML s názvem `Data.xml`, soubor bude vypadat podobně jako následující příklad kódu.  
  
 `<file name="Data.xml" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  Přidat atribut `type` do tohoto elementu a zadejte s hodnotou `data`.  
  
 `<file name="Data.xml" writeableType="applicationData" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  Opětovné podepsání manifestu aplikace pomocí páru klíčů nebo certifikátu a znovu podepsání manifestu nasazení.  
  
     Manifest nasazení musíte znovu podepsat, protože došlo ke změně jeho hodnoty hash manifestu aplikace.  
  
     **manifest aplikace Mage -s - CR cert_file - pwd heslo**  
  
     **manifest Mage -u nasazení manifestu - appm aplikace.**  
  
     **manifest nasazení Mage -s - CR Soubor_certifikátu - pwd heslo**  
  
2.  
  
### <a name="to-include-a-data-file-by-using-mageuiexe"></a>Chcete-li zahrnout datový soubor pomocí MageUI.exe  
  
1.  Přidáte datový soubor do adresáře aplikace s ostatními soubory aplikace.  
  
2.  Obvykle adresáře aplikace bude adresář s názvem bez přípony s aktuální verzí nasazení – například v1.0.0.0.  
  
3.  Na **soubor** nabídky, klikněte na tlačítko **otevřete** otevřete manifest aplikace.  
  
4.  Vyberte **soubory** kartě.  
  
5.  V textovém poli v horní části karty zadejte adresář obsahující soubory aplikace a pak klikněte na tlačítko **vyplnit**.  
  
     Datový soubor se zobrazí v mřížce.  
  
6.  Nastavte **typ souboru** hodnotu datového souboru **Data**.  
  
7.  Uložte manifest aplikace a pak se znovu přihlaste soubor.  
  
     MageUI.exe vás vyzve k znovu podepsat soubor.  
  
8.  Opětovné podepsání manifestu nasazení  
  
     Manifest nasazení musíte znovu podepsat, protože došlo ke změně jeho hodnoty hash manifestu aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k místním i vzdáleným datům v aplikacích ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)