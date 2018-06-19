---
title: LPTEXTOUTPROC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- LPTEXTOUTPROC
helpviewer_keywords:
- SccMsgDataOnMessage structure
- SccMsgDataOnBeforeGetFile structure
- SccMsgDataIsCancelled structure
- LPTEXTOUTPROC callback function
- SccMsgDataOnAfterGetFile structure
ms.assetid: 2025c969-e3c7-4cf4-a5c5-099d342895ea
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 235d98ba6a5ca665857b8a18db5ca823ecc0c7c1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143524"
---
# <a name="lptextoutproc"></a>LPTEXTOUTPROC
Když uživatel provede operaci zdroj ovládacího prvku z uvnitř integrované vývojové prostředí (IDE), může modul plug-in správy zdroje mají být umístěny chyba nebo stavové zprávy týkající se operace. Modul plug-in seznam můžete zobrazit svůj vlastní okna zpráv pro tento účel. Ale pro další bezproblémovou integraci, modul plug-in můžete předat řetězce integrovaného vývojového prostředí, které zobrazí je v jeho nativní způsob zobrazení informací o stavu. Mechanismus pro toto je `LPTEXTOUTPROC` – ukazatel na funkci. Prostředí IDE implementuje tuto funkci (podrobněji popsané v následující) pro zobrazení stavů a chyb.  
  
 Prostředí IDE předá do zdrojového kódu modulu plug-in ukazatel funkce na tuto funkci, jako `lpTextOutProc` parametr při volání metody [SccOpenProject](../extensibility/sccopenproject-function.md). Během operace SCC, třeba uprostřed volání [SccGet](../extensibility/sccget-function.md) zahrnující mnoho souborů, modul plug-in můžete volat `LPTEXTOUTPROC` funkce, pravidelně předávání řetězce k zobrazení. Prostředí IDE může zobrazit tyto řetězce na stavovém řádku, v okně výstupu nebo v samostatném okně, podle potřeby. Volitelně může nebude moci zobrazit některé zprávy s IDE **zrušit** tlačítko. To umožňuje uživateli na tlačítko Storno a poskytuje prostředí IDE možnost předejte tyto informace zpátky do modulu plug-in.  
  
## <a name="signature"></a>Podpis  
 Prostředí IDE výstupu funkce má následující podpis:  
  
```cpp  
typedef LONG (*LPTEXTOUTPROC) (  
   LPSTR display_string,  
   LONG mesg_type  
);  
```  
  
## <a name="parameters"></a>Parametry  
 display_string  
 Textový řetězec k zobrazení. Tento řetězec nesmí být byla ukončena s znaků CR vrátit, nebo a odřádkování.  
  
 mesg_type  
 Typ zprávy. Následující tabulka uvádí podporované hodnoty tohoto parametru.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`SCC_MSG_INFO, SCC_MSG_WARNING, SCC_MSG_ERROR`|Zpráva považuje za informace, varování nebo chyba.|  
|`SCC_MSG_STATUS`|Zpráva se zobrazuje stav a mohou být zobrazeny ve stavovém řádku.|  
|`SCC_MSG_DOCANCEL`|Odeslané s řetězec žádné zprávy.|  
|`SCC_MSG_STARTCANCEL`|Zahájí zobrazení **zrušit** tlačítko.|  
|`SCC_MSG_STOPCANCEL`|Zastaví zobrazování **zrušit** tlačítko.|  
|`SCC_MSG_BACKGROUND_IS_CANCELLED`|Požádá IDE, pokud má být zrušena operace na pozadí: vrátí IDE `SCC_MSG_RTN_CANCEL` Pokud operace byla zrušena; jinak vrátí `SCC_MSG_RTN_OK`. `display_string` Parametr vložena jako [SccMsgDataIsCancelled](#LinkSccMsgDataIsCancelled) strukturu, která poskytuje modul plug-in zdrojového kódu.|  
|`SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE`|Poskytuje rozhraní IDE o souboru před načtením z verzí. `display_string` Parametr vložena jako [SccMsgDataOnBeforeGetFile](#LinkSccMsgDataOnBeforeGetFile) strukturu, která poskytuje modul plug-in zdrojového kódu.|  
|`SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE`|Poskytuje rozhraní IDE o souboru po má byl načteny z verzí. `display_string` Parametr vložena jako [SccMsgDataOnAfterGetFile](#LinkSccMsgDataOnAfterGetFile) strukturu, která poskytuje modul plug-in zdrojového kódu.|  
|`SCC_MSG_BACKGROUND_ON_MESSAGE`|Sdělíte rozhraní IDE aktuální stav operaci na pozadí. `display_string` Parametr vložena jako [SccMsgDataOnMessage](#LinkSccMsgDataOnMessage) strukturu, která poskytuje modul plug-in zdrojového kódu.|  
  
## <a name="return-value"></a>Návratová hodnota  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_MSG_RTN_OK|Řetězec zobrazila nebo operace byla úspěšně dokončena.|  
|SCC_MSG_RTN_CANCEL|Uživatel chce na tlačítko Storno.|  
  
## <a name="example"></a>Příklad  
 Předpokládejme, že volání IDE [SccGet](../extensibility/sccget-function.md) s dvacet názvy souborů. Modul plug-in zdrojového kódu se chce zabránit zrušení operace uprostřed get souboru. Po získání každý soubor, zavolá `lpTextOutProc`, předání informace o stavu na každý soubor a odešle `SCC_MSG_DOCANCEL` zpráv, pokud ji nemá stav do sestavy. Pokud kdykoli modul plug-in obdrží návratová hodnota `SCC_MSG_RTN_CANCEL` v prostředí IDE, zruší operaci get okamžitě, takže jsou načteny žádné další soubory.  
  
## <a name="structures"></a>Struktury  
  
###  <a name="LinkSccMsgDataIsCancelled"></a> SccMsgDataIsCancelled  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
} SccMsgDataIsCancelled;  
```  
  
 Tato struktura je odeslána s `SCC_MSG_BACKGROUND_IS_CANCELLED` zprávy. Použije se pro komunikaci ID operace na pozadí, které bylo zrušeno.  
  
###  <a name="LinkSccMsgDataOnBeforeGetFile"></a> SccMsgDataOnBeforeGetFile  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szFile;  
} SccMsgDataOnBeforeGetFile;  
```  
  
 Tato struktura je odeslána s `SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE` zprávy. Použije se název souboru o mají být načteny a ID operace na pozadí, který provádí načítání komunikace.  
  
###  <a name="LinkSccMsgDataOnAfterGetFile"></a> SccMsgDataOnAfterGetFile  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szFile;  
   SCCRTN sResult;  
} SccMsgDataOnAfterGetFile;  
```  
  
 Tato struktura je odeslána s `SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE` zprávy. Použije se pro komunikaci výsledek načítání zadaný soubor, jakož i ID operace na pozadí, která nebyla načítání. Návratové hodnoty pro najdete [SccGet](../extensibility/sccget-function.md) pro co lze zadat v důsledku.  
  
###  <a name="LinkSccMsgDataOnMessage"></a> SccMsgDataOnMessage  
 [C++]  
  
```  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szMessage;  
   BOOL bIsError;  
} SccMsgDataOnMessage;  
```  
  
 Tato struktura je odeslána s `SCC_MSG_BACKGROUND_ON_MESSAGE` zprávy. Použije se pro komunikaci aktuální stav operaci na pozadí. Stav je vyjádřena jako řetězec, který se má zobrazovat IDE, a `bIsError` označuje závažnost zprávy (`TRUE` pro chybovou zprávu; `FALSE` pro varování nebo informační zpráva). ID operace na pozadí odesílání stav je dán rovněž.  
  
## <a name="code-example"></a>Příklad kódu  
 Zde je stručný příklad volání `LPTEXTOUTPROC` k odeslání `SCC_MSG_BACKGROUND_ON_MESSAGE` zprávu, která zobrazuje postup přetypovat strukturu volání.  
  
```cpp  
LONG SendStatusMessage(  
    LPTEXTOUTPROC pTextOutProc,  
    DWORD         dwBackgroundID,  
    LPCTSTR       pStatusMsg,  
    BOOL          bIsError)  
{  
    SccMsgDataOnMessage msgData = { 0 };  
    LONG                result  = 0;  
  
    msgData.dwBackgroundOperationID = dwBackgroundID;  
    msgData.szMessage               = pStatusMsg;  
    msgData.bIsError                = bIsError;  
  
    result = pTextOutProc(reinterpret_cast<LPCTSTR>(&msgData), SCC_MSG_BACKGROUND_ON_MESSAGE);  
    return result;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Funkce zpětného volání, které implementují rozhraní IDE](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [Moduly plug-in správy zdrojového kódu](../extensibility/source-control-plug-ins.md)