---
title: Nástroj konfigurace zobrazení okna | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, configuring
- tool windows, appearance
ms.assetid: 502a4926-bb83-473e-94e2-8e833c5f8b53
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 175e2005047312f6815e90c21c60ab831c036064
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143690"
---
# <a name="tool-window-display-configuration"></a>Konfigurace zobrazení okna nástrojů
Když VSPackage zaregistruje okno nástroje, výchozí umístění, velikost, styl ukotvení a další informace, zda je zadáno v volitelné hodnoty. Další informace o nástroj registrace okna, najdete v části [nástroj Windows v registru](../extensibility/tool-windows-in-the-registry.md)  
  
## <a name="window-display-information"></a>Informace o zobrazení oken  
 Okno nástroje zobrazení základní konfigurace je uložená v až šest volitelné hodnoty:  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        <Version>\  
          ToolWindows\  
            <Tool Window GUID>\  
              (Default)       = reg_sz: <Package GUID>Name            = reg_sz: <name of tool window>Float           = reg_sz: <position>Style           = reg_sz: <dock style>Window          = reg_sz: <window GUID>Orientation     = reg_sz: <orientation>DontForceCreate = reg_dword: 0x00000000  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|Název|REG_SZ|"Krátký název místo"|Krátký název, který popisuje okno nástroje. Používá se jenom pro odkaz v registru.|  
|Plovoucí desetinná čárka|REG_SZ|"X1, Y1, X2, Y2"|Čtyři hodnoty oddělené čárkami. X1, Y1 je souřadnice levého horního rohu okna nástroje. X2, Y2 je souřadnice pravého dolního rohu. Všechny hodnoty jsou v souřadnice obrazovky.|  
|Styl|REG_SZ|"MDI"<br /><br /> "Float"<br /><br /> "Vazbu"<br /><br /> "– Záložkami"<br /><br /> "AlwaysFloat"|Klíčové slovo určující počáteční zobrazení stavu okno nástroje.<br /><br /> "MDI" = ukotven s okna MDI.<br /><br /> "Float" = číslo s plovoucí čárkou.<br /><br /> "Vazbu" = spojena se další okno (zadané v položce okno).<br /><br /> "– Záložkami" = v kombinaci s další okno nástroje.<br /><br /> "AlwaysFloat" = nelze ukotvit.<br /><br /> Další informace najdete v části komentáře níže.|  
|Okno|REG_SZ|*\<IDENTIFIKÁTOR GUID &GT;*|Identifikátor GUID časového období, do které okno nástroje propojený nebo na kartách. Identifikátor GUID může patřit k některé z oken, vlastní nebo jeden z windows v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE.|  
|orientace|REG_SZ|"Vlevo"<br /><br /> "Vpravo"<br /><br /> "Top"<br /><br /> "Dolů"|Projděte si část komentáře níže.|  
|DontForceCreate|REG_DWORD|0 nebo 1|Pokud je tato položka a její hodnota není nula, okno je načtena, ale není ihned zobrazit.|  
  
### <a name="comments"></a>Komentáře  
 Položka orientaci definuje pozice, kdy okno nástroje ukotvené při poklepání na jeho záhlaví. Pozice je relativní vzhledem ke okno zadané v položce okno. Pokud je položka styl nastavena na "Propojené", položka orientace může být "Vlevo", "Vpravo", "Top" nebo "Dolů". Pokud položka styl je "Tabbed", orientaci položka může být "vlevo" nebo "Vpravo" a určuje, kde se přidá na kartě. Pokud je styl položka "Float", okno nástroj nejdřív uvolnit. Při poklepání na záhlaví položky okno a orientaci platné a okno používá styl "Tabbed". Pokud je styl položka "AlwaysFloat", nelze ukotvit okno nástroje. Pokud je styl položka "MDI", panel nástrojů je propojený s oblasti MDI a okno Položka bude ignorována.  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        8.0Exp\  
          ToolWindows\  
            {A0C5197D-0AC7-4B63-97CD-8872A789D233}\  
              (Default)       = reg_sz: {DA9FB551-C724-11D0-AE1F-00A0C90FFFC3}  
              DontForceCreate = reg_dword: 0x00000000  
              Float           = reg_sz: 100,100,450,300  
              Name            = reg_sz: Bookmarks  
              Orientation     = reg_sz: Left  
              Style           = reg_sz: Tabbed  
              Window          = reg_sz: {34E76E81-EE4A-11D0-00A0C90FFFC3}  
```  
  
## <a name="tool-window-visibility"></a>Viditelnost okna nástrojů  
 Hodnoty v podklíči volitelné viditelnost určují nastavení viditelnosti okno nástroje. Názvy hodnot se používají k ukládání identifikátory GUID příkazy, které vyžadují viditelnost okna. Pokud je příkaz spuštěn, rozhraní IDE zaručuje, že okno nástroje je vytvořen a dostupná.  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        <Version>\  
          ToolWindows\  
            <Tool Window GUID>\  
              Visibility\  
                (Default) = reg_sz:  
                <GUID>    = reg_dword:  
                <GUID>    = reg_dword:  
                <GUID>    = reg_sz:  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|(Výchozí)|REG_SZ|Žádné|Nechte pole prázdná.|  
|*\<IDENTIFIKÁTOR GUID &GT;*|REG_DWORD nebo REG_SZ|popisný řetězec nebo 0.|Volitelné. Název této položky musí být identifikátor GUID příkazu nutnosti viditelnosti. Hodnota obsahuje jenom informativní řetězec. Obvykle je hodnota `reg_dword` nastaven na hodnotu 0.|  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        8.0Exp\  
          ToolWindows\  
            {EEFA5220-E298-11D0-8F78-00A0C9110057}\  
              Visibility\  
                (Default) = reg_sz:  
                {93694fa0-0397-11d1-9f4e-00a0c911004f} = reg_dword: 0x00000000  
                {9DA22B82-6211-11d2-9561-00600818403B} = reg_dword: 0x00000000  
                {adfc4e66-0397-11d1-9f4e-00a0c911004f} = reg_dword: 0x00000000  
```  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)