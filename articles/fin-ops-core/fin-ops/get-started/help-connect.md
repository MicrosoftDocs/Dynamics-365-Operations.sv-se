---
title: Konfigurera hjälpupplevelsen för Ekonomi och Drift-appar
description: I den här artikeln finns information om komponenterna i hjälpsystemet för vissa Microsoft Dynamics 365-appar.
author: margoc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b002b374e5da619460c496b8f0d7a70b7194afd0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900141"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>Konfigurera hjälpupplevelsen för Ekonomi och Drift-appar

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

I den här artikeln finns en översikt över komponenterna i hjälpsystemet för Ekonomi och Drift-appar, t.ex. Microsoft Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce och Dynamics 365 Human Resources. Ämnet förklarar även hur du ansluter dessa komponenter samt tillhandahåller en sammanfattning av processen för att skapa egen hjälp.

## <a name="help-architecture"></a>Hjälparkitektur

Ekonomi och Drift-appar innehåller begreppsmässiga översikter och andra ämnen som publiceras på [Microsoft Dynamics 365 dokumentation](/dynamics365/)-webbplatsen. Du når detta innehåll från **Hjälp**-fönstret i produkten. Följande bild visar delarna i hjälpsystemet.

[![Hjälparkitektur.](./media/help-architecture.png)](./media/help-architecture.png)

Hjälpsystemet i produkten hämtar artiklar från docs.microsoft.com och andra anslutna webbplatser. Det tar också med uppgiftsguider som lagras i BPM (affärsprocessmodelleraren) i Microsoft Dynamics Lifecycle Services (LCS).

## <a name="adding-task-guides"></a>Lägga till uppgiftsguider

> [!NOTE]
> Fliken **Uppgiftsguider** finns för närvarande inte i Human Resources eller Commerce. <!--We are currently working to enable this functionality in a future release.--> Uppgiftsguiderna i Komma igång i Human Resources täcker emellertid fortsatt basfunktionerna. Procedurhjälp för såväl Human Resources som Commerce finns att tillgå på [Microsoft Dynamics 365 dokumentation](/dynamics365/)-webbplatsen.

På sidan **Systemparametrar** kan systemadministratörer konfigurera åtkomst till relevanta bibliotek för uppgiftsguider för en implementering.

> [!NOTE]
> - Om du vill konfigurera Hjälp måste du vara inloggad på ett konto i samma klientorganisation där appen distribueras.
> - Det går inte att ansluta till ett LCS-bibliotek från en instans av appen som körs på en virtuell hårddisk (VHD).

[![Formulär för systemparametrar med hjälpinställningar.](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Om du vill konfigurera uppgiftsguider för en lösning följer du instruktionerna på sidan **Systemparametrar**.

> [!IMPORTANT]
> Första gången du öppnar fliken **Hjälp** måste du ansluta till Lifecycle Services. Se till att välja länken i mitten av formuläret, vänta på anslutningen, stäng dialogrutan och välj sedan **OK** för att komma till sidan **Systemparametrar**.
>
> [![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png "Anslut till LCS.")](./media/connect-to-lcs-crop.png)

1. Välj Lifecycle Services-projektet att ansluta till.
2. Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.
3. Välj BPM-bibliotekens visningsordning. Visningsordningen bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.

När du har slutfört dessa steg kan du öppna fönstret **Hjälp** och klicka på fliken **Uppgiftsguider**. Du kan nu se de uppgiftsguider som gäller den sida som du för tillfället befinner dig på i Ekonomi och Drift-appar. Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.

### <a name="showing-translated-task-guides"></a>Visa översatta uppgiftsguider

Översatta uppgiftsguider medföljde för första gången i APQC Unified Library-versionen i maj 2016, samt i Komma igång-biblioteket. Om du vill se hjälpen för den lokaliserade uppgiftsguiden ska du se till att din Dynamics 365 for Operations-lösning är ansluten till maj 2016-biblioteket. Användare kan byta det språk som en uppgiftsguide visas i genom att byta språkinställning under **Alternativ** &gt; **Inställningar**.

> [!NOTE]
> Fastän många uppgiftsguider har översatts visas inte namnen på de översatta uppgiftsguiderna för närvarande i klienten. I biblioteket från maj 2016 finns dessutom översättningar endast för de uppgiftsguider som släpptes i februari 2016. Microsoft kommer att släppa ett uppdaterat bibliotek som omfattar fler översättningar.
>
> - Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.
> - Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.

## <a name="adding-custom-help"></a>Lägga till anpassad hjälp

Du kan använda uppgiftsguiderna för att skapa anpassad hjälp eller ansluta en anpassad hjälpwebbplats till fönstret **Hjälp**.

### <a name="create-custom-help-by-using-task-guides"></a>Skapa anpassad hjälp genom att använda uppgiftsguider

Du kan skapa anpassad hjälp för dina stödda appar genom att skapa uppgiftsinspelningar som speglar din implementering och sedan spara dem i ett bibliotek för arbetsprocesser i LCS. Du kan inte skapa anpassade uppgiftsguider för Human Resources.

Om du är partner och befordrar ett bibliotek till ett företagsbibliotek och inkluderar det i en lösning, blir det tillgängligt även för dina kunder. Du kan också göra en kopia av APQC Unified Library och sedan öppna uppgiftsinspelningarna i din kopia, redigera dem och sedan spara dina ändringar. Mer information finns i [Uppgiftsinspelarresurser](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-help-site"></a>Ansluta en anpassad hjälpwebbplats

Ekonomi och Drift-appar används sällan i sina färdiga formulär. Lösningen är i stället anpassad och utökad så att den passar organisationens behov. Du kan också anpassa och utöka hjälpfunktionen. Du kan till exempel lägga till egen hjälp i produktens egna **Hjälp**-fönster.

Microsoft tillhandahåller en verktygslåda som hjälper dig att distribuera och ansluta anpassad hjälp till **Hjälp**-fönstret. Information om hur du ställer in en anpassad hjälp-lösning som är ansluten till **Hjälp**-fönstret finns i [Översikt över anpassad hjälp](../../dev-itpro/help/custom-help-overview.md).

Om du vill samarbeta med Microsoft angående verktyg och processer för att anpassa Hjälpen fyller du i formuläret på [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Se även

[Hjälpsystem](help-overview.md)  
[Anpassad Hjälp – en översikt](../../dev-itpro/help/custom-help-overview.md)  
[Uppgiftsinspelarresurser](../../dev-itpro/user-interface/task-recorder.md)  
[Skapa dokumentation eller utbildning med Uppgiftsinspelare](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Anpassad GitHub-databas för Hjälp](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
