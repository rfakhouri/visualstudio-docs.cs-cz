---
title: Poskytuje kontext služby jazyka pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - language service context
ms.assetid: daa2df22-9181-4bad-b007-a7d40302bce1
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4471b71b612008ba7d0733c92286415cd3c3f6b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68193863"
---
# <a name="providing-a-language-service-context-by-using-the-legacy-api"></a>Poskytnutí kontextu jazykové služby pomocí zastaralého rozhraní API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Existují dvě možnosti pro službu jazyka poskytnout uživatelům pomocí kontextu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] základní editor: Zadejte text značky kontextu, nebo zadejte všechny místní uživatele. Rozdíly mezi jednotlivými jsou uvedeny zde.  
  
 Další informace o dodává kontext k služba jazyka, která je připojená k vlastní editor, naleznete v tématu [jak: Poskytuje kontext pro editory](../extensibility/how-to-provide-context-for-editors.md).  
  
## <a name="provide-text-marker-context-to-the-editor"></a>Zadejte Text značky kontextu editoru  
 K zajištění chyby kompilátoru indikován text značky v kontextu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] základní editor, implementujte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> rozhraní. V tomto scénáři služba jazyka poskytuje kontext, jenom když je ukazatel myši na text značky. To umožňuje editoru poskytnout – klíčové slovo na pozici kurzoru do **dynamická Nápověda** okno s žádné atributy.  
  
## <a name="provide-all-user-context-to-the-editor"></a>Zadejte všechny místní uživatele do editoru  
 Pokud vytváříte služba jazyka a používají [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] základní editor, pak můžete implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> rozhraní poskytuje kontext pro vaši službu jazyka.  
  
 Pro implementaci `IVsLanguageContextProvider`, místní kontejner (kolekci) je připojen k editor, který je zodpovědný za automatickou aktualizaci kontejneru kontextu. Když **dynamická Nápověda** okno volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.Update%2A> rozhraní na tento kontext kontejner objektů a dat v době nečinnosti, kontejner a kontext dat dotazuje editor pro aktualizaci. Editor jazyková služba poté oznámí, že by měl aktualizovat editoru a předává ukazatel do kontejneru objektů a dat v kontextu. To se provádí pomocí volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider.UpdateLanguageContext%2A> metodu z editoru služba jazyka. Použití ukazatele do kontejneru objektů a dat v kontextu, služba jazyka lze nyní přidávat a odebírat atributy a klíčová slova. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider>.  
  
 Existují dva různé způsoby, jak implementovat `IVsLanguageContextProvider`:  
  
- Zadejte klíčové slovo do kontejneru a kontext dat  
  
   Při volání editor k aktualizaci kontejneru kontextu, předejte příslušná klíčová slova a atributy a pak se vraťte `S_OK`. Tuto hodnotu nastaví editor zachovat – klíčové slovo a atribut kontextu, spíše než poskytují klíčové slovo na pozici kurzoru do kontejneru objektů a dat v kontextu.  
  
- Získat klíčové slovo from – klíčové slovo na pozici kurzoru  
  
   Při volání editor k aktualizaci kontejneru a kontext dat, předejte příslušné atributy a pak se vraťte `E_FAIL`. Tuto hodnotu nastaví editor zachovat svoje atributy v kontejneru a kontextu, ale aktualizovat kontejner objektů a dat souvislosti s klíčovým slovem na pozici kurzoru.  
  
  Následující diagram ukazuje, jak se poskytuje kontext pro službu jazyka, který implementuje `IVsLanguageContextProvider`.  
  
  ![Obrázek LangServiceImplementation2](../extensibility/media/vslanguageservice2.gif "vsLanguageService2")  
  Kontext pro služby jazyka  
  
  Jak je vidět v diagramu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] základní text editor má kontejner kontext k němu připojená. Tento kontejner objektů a dat kontextu odkazuje na tři samostatné kontext kontejnery objektů a dat: služba jazyka, výchozí editor a text značky. Na jazykové služby a text značky kontext kontejnery objektů a dat obsahovat atributy a klíčová slova jazyka služby, pokud <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> rozhraní je implementováno a text značky Pokud <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> rozhraní je implementováno. Pokud jste neimplementuje některou z těchto rozhraní, editor poskytuje kontext pro klíčové slovo na pozici kurzoru v kontejneru a výchozí editor kontext.  
  
## <a name="context-guidelines-for-editors-and-designers"></a>Kontext pokyny pro editorů a návrhářů  
 Návrháři a editory, musíte zadat obecné – klíčové slovo pro editoru nebo návrháře oken. To se provádí tak, aby tématu nápovědy obecný, ale odpovídající, se zobrazí návrhář nebo editor po stisknutí klávesy F1. Editor musí kromě toho zadejte aktuální – klíčové slovo na pozici kurzoru nebo zadat podmínku klíče na základě aktuálního výběru. To se provádí, aby odkazovala na téma nápovědy pro text nebo prvek uživatelského rozhraní nebo vybrané zobrazí, když uživatel stiskne klávesu F1. Návrhář poskytuje kontext pro položky vybrané v návrháři, jako je například tlačítko na formuláři. Návrháři a editory musí také připojit ke službě jazyka jak je uvedeno v [Základy služby starší verze jazyka](../extensibility/internals/legacy-language-service-essentials.md).
