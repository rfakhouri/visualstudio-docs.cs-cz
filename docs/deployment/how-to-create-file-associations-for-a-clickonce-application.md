---
title: 'Postupy: Vytváření přidružení souborů pro aplikaci ClickOnce | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0526351d2b3e2c223aacbe0e58d9ee39bd1b19c4
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924561"
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>Postupy: Vytvoření přidružení souborů pro aplikaci ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]aplikace je možné přidružit k jedné nebo více příponám názvů souborů, aby se aplikace spustila automaticky, když uživatel otevře soubor těchto typů. Přidání podpory přípon názvů souborů do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace je jednoduché.

### <a name="to-create-file-associations-for-a-clickonce-application"></a>Vytvoření přidružení souborů pro aplikaci ClickOnce

1. Vytvořte aplikaci normálně nebo použijte existující [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]

2. Otevřete manifest aplikace pomocí textového editoru nebo editoru XML, jako je například Poznámkový blok.

3. `assembly` Vyhledejte element. Další informace naleznete v tématu [manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md).

4. Jako podřízený `assembly` prvek elementu `fileAssociation` přidejte element. `fileAssociation` Element má čtyři atributy:

   - `extension`: Přípona názvu souboru, kterou chcete přidružit k aplikaci.

   - `description`: Popis typu souboru, který se zobrazí v prostředí Windows Shell.

   - `progid`: Řetězec jednoznačně identifikující typ souboru, který se má označit v registru.

   - `defaultIcon`: Ikona, která se má použít pro tento typ souboru Ikona musí být přidána jako prostředek souboru v manifestu aplikace. Další informace najdete v tématu [jak: Zahrnutí datového souboru do aplikace](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)ClickOnce.

     Příklad `file` prvků a `fileAssociation` naleznete v tématu [ \<Association > element](../deployment/fileassociation-element-clickonce-application.md).

5. Pokud chcete aplikaci přidružit více než jeden typ souboru, přidejte další `fileAssociation` prvky. Všimněte si, `progid` že atribut by měl být pro každý z nich odlišný.

6. Po dokončení manifestu aplikace znovu podepište manifest. To lze provést z příkazového řádku pomocí nástroje *Mage. exe*.

    `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`

    Další informace naleznete v tématu [Mage. exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).

## <a name="see-also"></a>Viz také:
- [\<element > přidružení](../deployment/fileassociation-element-clickonce-application.md)
- [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md)
- [Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)