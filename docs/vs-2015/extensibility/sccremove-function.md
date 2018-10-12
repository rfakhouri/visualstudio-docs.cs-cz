---
title: Sccremove – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccRemove
helpviewer_keywords:
- SccRemove function
ms.assetid: 20830fdc-c0e9-4a5f-bf60-33f28874442f
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 85e1eb8a4929462e92d848738c4e6e2d15fbc209
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254010"
---
# <a name="sccremove-function"></a>SccRemove – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce odstraní soubory z systém správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccRemove(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 %{nfiles/  
 [in] Počet souborů podle `lpFileNames` pole.  
  
 lpFileNames  
 [in] Pole úplná místní cesta názvy souborů, které mají být odebrány.  
  
 lpComment  
 [in] Komentář, který se má použít u každého souboru odebírá.  
  
 fOptions  
 [in] Příkaz příznaky (nepoužívané).  
  
 pvOptions  
 [in] Možností správy zdrojového kódu plug-konkrétní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Odstranění bylo úspěšné.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není pod správou zdrojových kódů.|  
|SCC_E_OPNOTSUPPORTED|Systém správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_ISCHECKEDOUT|Soubor nelze odebrat, protože uživatel je aktuálně rezervovány.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže k provedení této operace.|  
|SCC_E_NONSPECIFICERROR|Obecná chyba; Soubor nebyl odstraněn.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce odebere soubory ze systému správy zdrojového kódu, ale nedojde k odstranění je z místního pevného disku uživatele.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)

