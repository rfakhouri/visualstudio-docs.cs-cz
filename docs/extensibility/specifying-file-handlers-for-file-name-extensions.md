---
title: "Určení souboru obslužné rutiny pro přípony názvu souboru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: file extensions, specifying file handlers
ms.assetid: e3de4730-a95c-465a-b3b2-92ca85364ad7
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5833285a3d9ce9df02dc0359379ea623054588a8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="specifying-file-handlers-for-file-name-extensions"></a>Určení souboru obslužné rutiny pro přípony názvu souboru
Existuje několik způsobů, jak zjistit, která zpracovává soubor, který má příponu souboru konkrétní aplikace. Příkazy OpenWithList a OpenWithProgids jsou dva způsoby, jak zadat soubor obslužných rutin pod položkou registru pro příponu souboru.  
  
## <a name="openwithlist-verb"></a>Příkaz OpenWithList  
 Když kliknete pravým tlačítkem na soubor v Průzkumníku Windows, uvidíte **otevřete** příkaz. Pokud je více než jeden produkt související s příponou, uvidíte **otevřít v** podnabídky.  
  
 Chcete-li spustit rozšíření nastavením OpenWithList klíč pro tuto příponu v HKEY_CLASSES_ROOT různé aplikace můžete zaregistrovat. Uvedené pod tímto klíčem pro příponu souboru aplikace se zobrazí pod **doporučená programy** nadpis v **otevřít v** dialogové okno. Následující příklad ukazuje aplikace zaregistrované otevřete .vcproj příponu souboru.  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithList\  
         devenv.exe  
```  
  
> [!NOTE]
>  U klíčů zadání aplikace se ze seznamu v části HKEY_CLASSES_ROOT\Applications.  
  
 Přidáním klíčem OpenWithList deklarovat, že vaše aplikace podporuje příponu souboru i v případě, že vlastnictví rozšíření převezme jiná aplikace. To může být v budoucích verzích vaší aplikace nebo jiná aplikace.  
  
## <a name="openwithprogids"></a>OpenWithProgIDs  
 Programové identifikátory (ProgID) jsou popisný verzích ID třídy, která identifikovat verzi aplikace nebo objektu COM. Každý společně vytvořitelné objekt by měl mít svůj vlastní ProgID. Například VisualStudio.DTE.7.1 spuštění Visual Studio .NET 2003 při spuštění VisualStudio.DTE.10.0 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Jako vlastník projektu typu nebo typu položky projektu musíte vytvořit ProgID specifické pro verzi pro vaše příponu souboru. Tyto identifikátory ProgID může být redundantní v tom, že více než jeden ProgID může spustit stejné aplikaci. Další informace najdete v tématu [registrace příkazy pro přípony názvu souboru](../extensibility/registering-verbs-for-file-name-extensions.md).  
  
 Použijte následující konvence pro verzí souboru ProgID předejdete duplikace s registrací od jiných dodavatelů:  
  
|Přípona souboru|Verzí ProgID|  
|--------------------|----------------------|  
|.Extension|ProductName. extension.versionMajor.versionMinor|  
  
 Můžete zaregistrovat jiné aplikace, které jsou možné otevřít konkrétní příponu přidáním verzí ProgID jako hodnoty HKEY_CLASSES_ROOT\\*\<rozšíření >*\OpenWithProgids klíč. Tento klíč registru, obsahuje seznam alternativní ProgID přidružené k příponě souboru. Aplikace přidružené k uvedené ProgID zobrazeny **otevřít v***název produktu* podnabídky. Pokud stejná aplikace je zadána v obou `OpenWithList` a `OpenWithProgids` slučuje duplicitní hodnoty klíče, operační systém.  
  
> [!NOTE]
>  `OpenWithProgids` Klíčů je podporovaná jen v systému Windows XP. Protože jinými operačními systémy Ignorovat tento klíč, nepoužívejte ho jako pouze registrace pro obslužné rutiny souborů. Tento klíč použijte zajistit lepší uživatelské prostředí v systému Windows XP.  
  
 Přidejte požadované ProgID jako hodnoty typu REG_NONE. Následující kód představuje příklad, registrace ProgID pro přípony souborů (. *ext*).  
  
```  
HKEY_CLASSES_ROOT\  
   .ext\  
      (default)="MyProduct.ext.14.0"  
      OpenWithProgids  
         progid        REG_NONE (zero-length binary value)  
         otherprogid   REG_NONE (zero-length binary value)  
```  
  
 ProgID zadaný jako výchozí hodnota pro příponu souboru je výchozí popisovač souboru. Pokud změníte ProgID pro příponu souboru, která odeslaná z předchozí verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo které mohou být převzaty ostatní aplikace a pak je nutné zaregistrovat `OpenWithProgids` klíč pro vaše přípona souboru a zadejte nové ProgID v seznamu spolu s původní ProgID, které podporujete. Příklad:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithProgids  
         vcprojfile              //old progid  
         VisualStudio.vcproj.12.0 //old progid  
         VisualStudio.vcproj.14.0 //new progid  
```  
  
 Pokud starý ProgID má příkazy, které jsou s ním spojená, pak tyto příkazy se také zobrazí v části **otevřít v** *název produktu* v místní nabídce.  
  
## <a name="see-also"></a>Viz také  
 [O přípony názvů souborů](../extensibility/about-file-name-extensions.md)   
 [Registrace příkazy pro přípony názvu souboru](../extensibility/registering-verbs-for-file-name-extensions.md)