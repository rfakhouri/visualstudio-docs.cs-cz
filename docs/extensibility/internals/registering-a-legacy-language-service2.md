---
title: Registrace starší verze jazyka Service2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, language services
- language services, registry information
- registry, language services
ms.assetid: ca312aa3-f9f1-4572-8553-89bf3a724deb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6cb7750f55bd9175c552aa765d21b1334f5f1dfe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134136"
---
# <a name="registering-a-legacy-language-service"></a>Registrace služby jazyk starší verze
V následujících částech najdete seznam položky registru pro různé jazyky možnosti služby, které jsou k dispozici v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 V následujícím seznamu položky registru *VS Reg kořenové* rovná HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*X.Y*, kde *X.Y* je [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] číslo verze.  
  
## <a name="registry-entries-for-language-service-options"></a>Položky registru pro možnosti služby jazyk  
 *VS Reg kořenové*\Languages\Language služby\\*název jazyka* klíč může obsahovat následující hodnoty.  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|(Výchozí)|REG_SZ|*\<IDENTIFIKÁTOR GUID &GT;*|Identifikátor GUID služby jazyk.|  
|LangResID|REG_DWORD|0x0 0xffff|Řetězec resource identifier (ResID) textu název jazyka.|  
|Balíček|REG_SZ|*\<IDENTIFIKÁTOR GUID &GT;*|Identifikátor GUID VSPackage.|  
|ShowCompletion|REG_DWORD|0-1|Určuje, zda **dokončování** možnosti v **možnosti** jsou povoleny dialogové okno.|  
|ShowSmartIndent|REG_DWORD|0-1|Určuje, zda možnost vybrat **inteligentní** odsazení v **možnosti** dialogové okno je povoleno.|  
|RequestStockColors|REG_DWORD|0-1|Určuje, zda vlastní nebo výchozí barvy se používají k barvu klíčová slova.|  
|ShowHotURLs|REG_DWORD|0-1|Určuje, jestli uživatel může kliknout na adresy URL.|  
|Ve výchozím nastavení týkají bez aktivní adresy URL|REG_DWORD|0-1|Určuje počáteční nastavení **povolit navigační adresa URL jedním kliknutím** možnost **možnosti** dialogové okno.|  
|DefaultToInsertSpaces|REG_DWORD|0-1|Určuje, zda je služba jazyka, "Vložit mezery" jako jeho výchozí kartě možnost.|  
|ShowDropdownBarOption|REG_DWORD|0-1|Povolí nebo zakáže **navigační panel** možnost **možnosti** dialogu, který zobrazí nebo skryje **navigační panel**.|  
|V okně pro jeden kód|REG_DWORD|0-1|Povolí nebo zakáže **nové okno** volba v **okno** nabídku pro služba jazyka.|  
|EnableAdvancedMembersOption|REG_DWORD|0-1|Povolí nebo zakáže **možnosti** nastavení dialogového pro **Skrýt rozšířené členy**.|  
|Podpora CF_HTML|REG_DWORD|0-1|Určuje, zda editor umožňuje kopírování a vkládání dat ve formátu HTML.|  
|EnableLineNumbersOption|REG_DWORD|0-1|Určuje, zda **čísla řádků** možnosti v **možnosti** dialogové okno je povolený pro služba jazyka.|  
|HideAdvancedMembersByDefault|REG_DWORD|0-1|Určuje, zda jsou v seznamy dokončení skryté členy rozšířené úrovně například privátní pole.|  
|ShowBraceCompletion|REG_DWORD|0-1|Určuje, zda **složených závorek dokončení** možnost **možnosti** dialogové okno je povoleno.|  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      C/C++\  
        (Default)             = reg_sz:{B2F072B0-ABC1-11D0-9D62-00C04FD9DFD9}  
        LangResID             = reg_dword:0x00000000  
        Package               = reg_sz:{8C2EA640-ABC1-11D0-9D62-00C04FD9DFD9}  
        ShowCompletion        = reg_dword:0x00000001  
        ShowSmartIndent       = reg_dword:0x00000001  
        ShowDropdownBarOption = reg_dword:0x00000001  
```  
  
## <a name="registry-entries-for-debugger-languages-options"></a>Položky registru pro jazyky možností ladicího programu  
 *VS Reg kořenové*\Languages\Language služby\\*název jazyka*\Debugger jazyky\\*GUID*\ klíč může obsahovat následující hodnoty.  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|(Výchozí)|REG_SZ|text|Výchozí hodnota slouží k dokumentu název jazyka. Název tohoto klíče je identifikátor GUID vyhodnocovací filtr výrazů, který má odpovídající záznam v  *\<VS Reg kořenové >* \AD7Metrics\Expression vyhodnocování.|  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      C/C++\  
        Debugger Languages\  
          {3A12D0B7-C26C-11D0-B442-00A0244A1DD2}\  
            (Default) = reg_sz:C++  
```  
  
## <a name="registry-entries-for-editor-tools-options"></a>Položky registru pro možnosti nástrojů editoru  
 Můžete přidat klíče registru pod klíčem EditorToolsOptions pro stránky vlastností a vlastnost uzly. Tyto klíče a jejich hodnoty identifikovat stránky vlastností v **možnosti** dialogové okno (na **nástroje** nabídky) používané ke konfiguraci služby jazyk. V následujícím příkladu *název stránky* je název stránky vlastností a *název uzlu* je název uzlu ve stromu na **možnosti** dialogové okno. Vstupní stránky a uzel položka je třeba zadat samostatně.  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|(Výchozí)|REG_SZ|resID|Lokalizované zobrazovaný název této stránky možnost. Název může být literál text nebo #`nnn`, kde `nnn` je řetězec ID prostředku v satelitní knihovny DLL z zadaný VSPackage.|  
|Balíček|REG_SZ|*GUID*|Identifikátor GUID VSPackage, který implementuje tuto stránku možnosti.|  
|Stránka|REG_SZ|*GUID*|Identifikátor GUID stránku vlastností požadovat od VSPackage voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> metoda. Pokud tato položka registru neexistuje, popisuje klíč registru uzlu, ne stránku.|  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      CSharp\  
        EditorToolsOptions\  
          Formatting\  
            (Default) = reg_sz:#242  
            Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
            General\  
              (Default) = reg_sz:#255  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{3EB2CC0B-033E-4D75-B26A-B2362C25227E}  
            Indentation\  
              (Default) = reg_sz:#250  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{5E21D017-6D2A-4114-A1F1-C923F001CBBB}  
            Newlines\  
              (Default) = reg_sz:#253  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{607D8062-68D1-41E4-9A35-B5E7F14D0481}  
```  
  
## <a name="registry-entries-for-file-name-extension-options"></a>Položky registru pro možností příponu názvu souboru  
 Položka pro tuto příponu by měla obsahovat úvodní tečku, například ".myext".  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|(Výchozí)|REG_SZ|*GUID*|Identifikátor GUID služby pro službu výchozí jazyk pro tento typ příponu názvu souboru.|  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    File Extensions\  
      .cpp\  
        (Default) = {B2F072B0-ABC1-11D0-9D62-00C04FD9DFD9}  
```  
  
## <a name="registry-entries-for-editor-options"></a>Položky registru pro možnosti editoru  
 *VS Reg kořenové*\Editors klíč může obsahovat následující hodnoty:  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|(Výchozí)|REG_SZ|""|Nepoužívané; můžete použít a zadat své jméno sem dokumentaci.|  
|DefaultToolboxTab|REG_SZ|""|Název karty sada nástrojů, aby výchozí, když je aktivní editor.|  
|displayName|REG_SZ|resID|Název zobrazený v **otevřít v** dialogové okno. Název je ID prostředku řetězec nebo název ve standardním formátu.|  
|ExcludeDefTextEditor|REG_DWORD|0-1|Použít pro **otevřít v** příkazu nabídky. Pokud nechcete seznamu textového editoru výchozí v seznamu dostupných editory pro určitý typ souboru, nastavte tuto hodnotu na 1.|  
|LinkedEditorGUID|REG_SZ|*\<IDENTIFIKÁTOR GUID &GT;*|Použít pro všechny jazykové služby, můžete otevřít soubor s podporou kódové stránky. Například pokud otevřete soubor s příponou .txt pomocí **otevřete s** příkazů, možnosti jsou k dispozici pro použití editoru zdrojového kódu a bez kódování.<br /><br /> Zadaný název podklíč identifikátor GUID je pro objekt factory editoru codepage; zadaný v tomto klíči registru konkrétní propojené identifikátor GUID je pro objekt pro vytváření pravidelných editor. Účelem této položky je, že pokud IDE nelze otevřít soubor pomocí editoru výchozí, rozhraní IDE pokusí se použít další editor v seznamu. Tohoto další editoru by neměl být objekt factory editoru kódové stránky, protože tento objekt factory editoru je v podstatě stejný jako objekt factory editoru, který selhal.|  
|Balíček|REG_SZ|*\<IDENTIFIKÁTOR GUID &GT;*|Identifikátor GUID VSPackage pro ResID zobrazovaný název.|  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      (Default)            = reg_sz:Html Editor with Encoding  
      DefaultToolboxTab    = reg_sz:HTML  
      DisplayName          = reg_sz:#20101  
      LinkedEditorGUID     = reg_sz:{C76D83F8-A489-11D0-8195-00A0C91BBEE3}  
      Package              = reg_sz:{1B437D20-F8FE-11D2-A6AE-00104BCC7269}  
```  
  
## <a name="registry-entries-for-logical-view-options"></a>Položky registru pro možnosti logické zobrazení  
 *VS Reg kořenové*\Editors\\*grafického uživatelského rozhraní editoru >* \LogicalViews klíč může obsahovat následující hodnoty.  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|(Výchozí)|REG_SZ||Nepoužívá se.|  
|*\<IDENTIFIKÁTOR GUID &GT;*|REG_SZ|""|Klíč k logické zobrazení podporováno. Můžete mít jako mnoho z těchto podle potřeby. Název položky registru je, co je důležité, není hodnotu, která je vždy prázdný řetězec.|  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      LogicalViews\  
       (Default) = reg_sz:  
       {7651a700-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a701-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a702-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a703-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
```  
  
## <a name="registry-entries-for-editor-extension-options"></a>Položky registru pro rozšíření editoru možnosti  
 *VS Reg kořenové*\Editors\\*Editor GUID*\Extensions klíč může obsahovat následující hodnoty. Přípona souboru není obsahovat úvodní tečku.  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|(Výchozí)|REG_SZ||Nepoužívá se.|  
|*\<ext >*|REG_DWORD|0-0xffffffff|Relativní priorita tohoto rozšíření. Pokud dva nebo více jazyků sdílet stejnou příponu, je zvolený jazyk s vyšší prioritou.|  
  
 Kromě toho je aktuální uživatel výchozí výběr pro editor uložený v HKEY_Current_User\Software\Microsoft\VisualStudio\\*X.Y*\Default editory\\*ext*. Identifikátor GUID služby vybraný jazyk se vlastní položku. To má přednost před pro aktuálního uživatele.  
  
### <a name="example"></a>Příklad  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      Extensions\  
       (Default) = reg_sz:  
       *         = reg_dword:0x00000018  
       html      = reg_dword:0x00000027  
       shtm      = reg_dword:0x00000027  
       shtml     = reg_dword:0x00000027  
```  
  
## <a name="registry-entries-for-managed-package-framework-language-service-options"></a>Položky registru pro spravované balíček Framework jazykového služby  
 Následující položky registru jsou specifické pro třídy služeb spravované balíček framework (MPF) jazyk. Tyto položky registru indikovat podporu ve službě jazyk pro různé funkce IntelliSense a další pokročilé funkce úpravy.  
  
 Tyto položky registru jsou přístupné prostřednictvím <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy.  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|CodeSense|REG_DWORD|0-1|Podpora pro operace IntelliSense.|  
|MatchBraces|REG_DWORD|0-1|Podpora pro odpovídající jazyk páry například složené závorky, kulaté závorky a hranaté závorky.|  
|QuickInfo|REG_DWORD|0-1|Podpora pro operaci rychlé informace technologie IntelliSense.|  
|ShowMatchingBrace|REG_DWORD|0-1|Podpora s dvojicí odpovídající jazyk ve stavovém řádku.|  
|MatchBracesAtCaret|REG_DWORD|0-1|Podpora pro zobrazení odpovídající dvojice jazyků, obvykle prostřednictvím zvýraznění dva elementy.|  
|MaxErrorMessages|REG_DWORD|0-n|Maximální počet chyb, které lze zobrazit v **seznam chyb** okno.|  
|CodeSenseDelay|REG_DWORD|0-n|Počet milisekund pro zpoždění před zahájením žádné pozadí analýza operace IntelliSense.|  
|EnableAsyncCompletion|REG_DWORD|0-1|Podpora pro analýzu pozadí.|  
|EnableCommenting|REG_DWORD|0-1|Podpora pro přidávání poznámek na vybrané bloky textu a také znamená podpora uncommenting vybraný text.|  
|EnableFormatSelection|REG_DWORD|0-1|Podpora pro formátování textu, jako je například automaticky odsazení nebo upravte pozice složených závorek.|  
|AutoOutlining|REG_DWORD|0-1|Podpora osnovy (oblasti, které lze sbalit).|  
|MaxRegions|REG_DWORD|0-n|Maximální počet skryté oblasti na soubor.|  
  
```  
ExampleHKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      XML\  
        (Default)             = reg_sz:{f6819a78-a205-47b5-be1c-675b3c7f0b8e}  
        MatchBraces           = reg_dword:0x00000001  
        QuickInfo             = reg_dword:0x00000001  
        ShowMatchingBrace     = reg_dword:0x00000001  
        MatchBracesAtCaret    = reg_dword:0x00000000  
        MaxErrorMessages      = reg_dword:0x00000064  
        CodeSenseDelay        = reg_dword:0x000001f4  
        MaxRegions            = reg_dword:0x0000000a  
```  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)