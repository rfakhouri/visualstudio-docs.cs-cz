---
title: "Poskytuje služby kontextu jazyka pomocí starší verze rozhraní API | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - language service context
ms.assetid: daa2df22-9181-4bad-b007-a7d40302bce1
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 79f58bf66e5d0a137738d0a2cc90f67a287246dc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="providing-a-language-service-context-by-using-the-legacy-api"></a>Poskytuje služby kontextu jazyka pomocí starší verze rozhraní API
Existují dvě možnosti pro službu jazyk zajistit pomocí kontextu uživatele [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor: Zadejte text značky kontextu, nebo zadejte všechny kontextu uživatele. Rozdíly mezi jednotlivými jsou zde popsané.  
  
 Další informace o poskytuje kontext, který má služba jazyka, která je připojena k vlastní editor najdete v tématu [postup: Zadejte kontext pro editory](../extensibility/how-to-provide-context-for-editors.md).  
  
## <a name="provide-text-marker-context-to-the-editor"></a>Zadejte Text značky kontextu do editoru  
 Stanovit chyby kompilátoru indikován značek text v kontextu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> rozhraní. V tomto scénáři služba jazyka poskytuje kontext, pokud se ukazatel na text značku. To umožňuje zajistit – klíčové slovo na pozici kurzoru do editoru **dynamické nápovědy** okno s žádné atributy.  
  
## <a name="provide-all-user-context-to-the-editor"></a>Zadejte všechny kontextu uživatele do editoru  
 Pokud vytváříte jazykové služby a používají [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor, pak můžete implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> rozhraní zajistit kontextu služby jazyk.  
  
 K provedení `IVsLanguageContextProvider`, kontejner kontextu (kolekce) je připojen k editor, který je zodpovědný za aktualizace kontejneru kontextu. Když **dynamické nápovědy** okno volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.Update%2A> rozhraní na tento kontejner kontextu v době nečinnosti, kontejneru kontextu dotazuje editor pro aktualizaci. Editor poté oznámí služba jazyka, že by měl aktualizovat editoru a předá ukazatel kontejneru kontextu. To se provádí volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider.UpdateLanguageContext%2A> metoda z editoru ke službě jazyk. Pomocí ukazatele kontejneru kontextu, služba jazyka teď můžete přidat a odebrat atributy a klíčová slova. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider>.  
  
 Existují dva různé způsoby, jak implementovat `IVsLanguageContextProvider`:  
  
-   Zadejte klíčové slovo do kontejneru kontextu  
  
     Při volání editoru k aktualizaci kontejneru kontextu, předejte odpovídající klíčová slova a atributy a pak se vraťte `S_OK`. Tato návratovou hodnotu dá pokyn editoru zachovat váš kontext – klíčové slovo a atribut, nikoli poskytují – klíčové slovo na pozici kurzoru do kontejneru kontextu.  
  
-   Získat klíčové slovo z – klíčové slovo na pozici kurzoru.  
  
     Při volání editoru k aktualizaci kontejneru kontextu, předejte příslušné atributy a pak se vraťte `E_FAIL`. Tato návratovou hodnotu dá pokyn editoru uchovávat vaše atributů v kontextu kontejneru, ale aktualizace kontejneru kontext pomocí klíčového slova na pozici kurzoru.  
  
 Následující diagram ukazuje, jak se poskytuje kontext pro službu jazyk, který implementuje `IVsLanguageContextProvider`.  
  
 ![Obrázek LangServiceImplementation2](../extensibility/media/vslanguageservice2.gif "vsLanguageService2")  
Kontext pro služba jazyka  
  
 Jak je vidět v diagramu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní textový editor má kontejner kontext k němu připojen. Tento kontejner kontextu odkazuje na tři samostatné dílčí kontext obalů: služba jazyka, editor výchozího a text značky. Sáčků jazykové služby a text. značky dílčí kontext obsahovat atributy a klíčová slova jazyka služby, pokud <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> rozhraní je implementováno, text značky a pokud <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> rozhraní je implementováno. Pokud není implementovat kterékoli z těchto rozhraní, editor poskytuje kontext pro klíčové slovo na pozici kurzoru v kontejneru výchozí editor dílčí kontext.  
  
## <a name="context-guidelines-for-editors-and-designers"></a>Kontext pokyny pro editory a návrháře  
 Editory a návrháři musíte zadat pro editor nebo návrháře okna Obecné – klíčové slovo. To se provádí tak, aby tématu nápovědy Obecné, ale odpovídající, se po stisknutí klávesy F1 zobrazí návrháře nebo editor. Editor musí, kromě toho zadejte aktuální – klíčové slovo na pozici kurzoru nebo zadejte klíče termín, na základě aktuálního výběru. Důvodem je, že bude potřeba zajistit, aby odkazoval na téma nápovědy pro text nebo elementu uživatelského rozhraní, a vybrali zobrazí při stisknutí klávesy F1. Návrhář poskytuje kontext pro položky vybrané v návrháři, jako je tlačítko ve formuláři. Editory a návrhářů, musí také připojit ke službě jazyk jak je uvedeno v [starší verze jazyka služby Essentials](../extensibility/internals/legacy-language-service-essentials.md).