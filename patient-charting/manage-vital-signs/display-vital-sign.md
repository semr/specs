#####Use Case ID: UC-PCS26
#####Use Case Name: Display Vital Sign

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Patient

**Stakeholders:**              Physician, Patient, Healthcare Provider, Order Filler

**Purpose:**                   The main intent of this use case is to display vital sign.

**Pre Condition:**             User must be identified and authenticated.

**Post Condition:**            Vital sign details will be displayed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Display Vital Sign)**

1. User requests to display vital sign.
2. System displays the list of patient’s vital signs.
3. User selects an appropriate vital sign.
4. System not only displays the vital sign but also indicates to the user when a vital sign measurement falls outside a preset normal range set by the authorized user.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Type is weight or height**

1. Repeat 1-3 steps of main scenario.
2. System then performs the following actions:
  * Displays the vital sign measurement
  * Indicates to the user when a vital sign measurement falls outside a preset normal range.
  * Display graph of height or weight over time.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.15, AM 08.24

_______________________________________________________________
**Reference Hl7 RMIM :** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![RIM Observation](https://f.cloud.github.com/assets/5391320/1371906/f29d7928-3a45-11e3-9b3c-a6611ba51bd6.png)

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![observation fhir resource](https://f.cloud.github.com/assets/5391320/1371904/e853986c-3a45-11e3-830b-7d08e9656b25.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template **"Objective Section"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Vital Signs (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-SECTION.vital_signs.v1

concept
	[at0000]	-- Vital signs
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Sebastian Garde">
				["organisation"] = <"Ocean Informatics">
				["email"] = <"sebastian.garde@oceaninformatics.com">
			>
		>
	>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"2006-03-14">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"A heading or section which can only contain observations considered to be vital signs. This group of observations is a common set in medicine, and while these often occur separately in health records, when they are measured together this is a significant assessment of wellbeing.">
			use = <"An organisational heading for vital signs.">
			keywords = <"blood pressure", "temperature", "pulse", "oxygen saturation", "respirations", "observations", "vital", "signs">
			misuse = <"Does not need to be used to record these entries separately.">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"Rubrik oder Abschnitt, der nur Observationen beinhalten kann, die als Vitalparameter gelten. Diese Gruppe von Observationen ist eine in der Medizin allgemein gebräuchliche Menge. Während die einzelnen Messungen in Gesundheitsakten oft getrennt vorkommen, bilden sie zusammen gemessen eine bedeutsame Beurteilung des Zustandes der Person.">
			use = <"Eine organisatorische Rukrik (Section) für Vitalparameter">
			keywords = <"Blutdruck", "Temperatur", "Puls", "Sauerstoffsättigung", "Atmung", "Observationen", "Vital", "Parameter">
			misuse = <"Muss nicht benutzt werden, um die verschiedenen Messungen getrennt voneinander aufzuzeichenen.

">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <>
	other_details = <
		["MD5-CAM-1.0.1"] = <"432A350497E9ACFB3D142F0D63CFB505">
	>

definition
	SECTION[at0000] matches {	-- Vital signs
		items cardinality matches {1..*; unordered} matches {
			allow_archetype OBSERVATION[at0001] occurrences matches {0..*} matches {	-- Vital signs
				include
					archetype_id/value matches {/openEHR-EHR-OBSERVATION\.blood_pressure(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-OBSERVATION\.body_temperature(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-OBSERVATION\.indirect_oximetry(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-OBSERVATION\.respiration(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-OBSERVATION\.pulse(-[a-zA-Z0-9_]+)*\.v1/}
			}
			allow_archetype EVALUATION[at0002] occurrences matches {0..1} matches {	-- Synopsis
				include
					archetype_id/value matches {/openEHR-EHR-EVALUATION\.clinical_synopsis(-[a-zA-Z0-9_]+)*\.v1/}
			}
		}
	}


ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Vital signs">
					description = <"A group of observations that are recorded at the same time and record the blood pressure, pulse, temperature and other readings.">
				>
				["at0001"] = <
					text = <"Vital signs">
					description = <"Vital signs observations.">
				>
				["at0002"] = <
					text = <"Synopsis">
					description = <"Textual summary of vital signs.">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"Vitalparameter">
					description = <"Eine Gruppe von Observationen, die zur selben Zeit erfasst werden und den Blutdruck, Puls, Temperatur und andere Messungen beinhalten.">
				>
				["at0001"] = <
					text = <"*Vital signs(en)">
					description = <"*Vital signs observations.(en)">
				>
				["at0002"] = <
					text = <"*Synopsis(en)">
					description = <"*Textual summary of vital signs(en)">
				>
			>
		>
	>

```
Blood Pressure (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.blood_pressure.v1

concept
	[at0000]	-- Blood Pressure
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Sebastian Garde, Jasmin Buck">
				["organisation"] = <"Ocean Informatics, University of Heidelberg">
			>
		>
		["zh-cn"] = <
			language = <[ISO_639-1::zh-cn]>
			author = <
				["name"] = <"Chunlan Ma">
				["organisation"] = <"Ocean Informatics">
			>
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			author = <
				["name"] = <"Domingo Liotta">
				["organisation"] = <"Universidad de Morón">
				["email"] = <"domingo_liotta@hotmail.com">
			>
			accreditation = <"Universidad de Morón">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			author = <
				["name"] = <"Shahla Foozonkhah">
				["organisation"] = <"Ocean Informatics">
				["email"] = <"shahla.foozonkhah@oceaninformatics.com">
			>
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			author = <
				["name"] = <"Igor Lizunov">
				["email"] = <"i.lizunov@infinnity.ru">
			>
		>
		["ja"] = <
			language = <[ISO_639-1::ja]>
			author = <
				["name"] = <"Shinji Kobayashi">
				["email"] = <"skoba@moss.gr.jp">
			>
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			author = <
				["name"] = <"Marja Buur">
				["organisation"] = <"M.C.A.">
				["email"] = <"m.buur-krom@mca.nl">
			>
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			author = <
				["name"] = <"Jussara Rözsch">
				["organisation"] = <"OpenEHR  Foundation">
				["email"] = <"jussara.macedo@gmail.com">
			>
			accreditation = <"Medical Doctor, Psychiarist, Clinical Modeller, openEHR Diretor, ehealth infostructuture WG ccoordinator- brazilian  ehealth program">
		>
	>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"22/03/2006">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the systemic arterial blood pressure of an individual. ">
			use = <"Use to record all representations of systemic arterial blood pressure measurement, no matter which method or body location is used to record it. The archetype is intended to capture blood pressure measurements in all clinical scenarios - for example, self-measurement with a home blood pressure machine; an emergency assessment of systolic using palpation and a sphygmomanometer; measurements taken in clinical consultations or during exercise stress testing; and a series of measurements made by a machine in Intensive Care.   
There is a rich state model that supports interpretation of measurements through identifying patient position, exercise, confounding factors and angle of a tilt table in research. 
Named events have been limited to average over a 24 hour period, however templates can further constrain the default 'any event' to cater for specific requirements for blood pressure measurements such as recording Blood Pressure against specific points in time, or over a range of intervals (+/- mathematical functions).">
			keywords = <"observations", "measurement", "bp", "vital signs", "mean arterial pressure", "pulse pressure", "systolic", "diastolic", "RR", "NIBP">
			misuse = <"Not to be used for intravenous pressure.
Not to be used for the measurement of arterial blood pressure which is NOT a surrogate for arterial pressure in the systemic circulation eg specific measurement of right Pulmonary artery pressure.  
Use OBSERVATION.intravascular_pressure and related specialisations in both of these situations.">
			copyright = <"© openEHR Foundation">
		>
		["ja"] = <
			language = <[ISO_639-1::ja]>
			purpose = <"ヒトの全身血圧を記録するためのもの。全身の血圧を測定する代用として適切な方法により測定された縮期圧と拡張期についての記録">
			use = <"このアーキタイプを使って測定されるすべての血圧が記録される。運動負荷心電図やティルト台での測定にも利用できる豊かなステートモデルがある。">
			keywords = <"観察", "血圧", "測定">
			misuse = <"血管内圧のためには使用されない">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"Dient der Dokumentation des systemischen arteriellen Blutdrucks einer Person.">
			use = <"Alle Blutdruckmessungen werden unter Zuhilfenahme dieses Archetypen dokumentiert, unabhängig davon, welche Methode oder Körperstelle zur Messung benutzt wurden. Der Archetyp dient der Dokumentation des Blutdrucks in alle klinischen Szenarien - z.B. durch eine Blutdruckmaschine zuhause; eine Notfallmessung durch Palpation und ein Sphygmomanometer; Messungen beim Hausarzt oder im Rahmen von Belastungstests; sowie einer Serie von Messungen durch eine Maschine auf der Intensivstation.
Der Archetyp beinhaltet ein umfassendes Status-Modell, das die Interpretation der Messung unterstützt, indem Position, Anstrengung, Einflussfaktoren, Neigungswinkel angegeben werden können.
Benannte Ereignisse wurden auf den 24-stündigen Durchschnitt beschränkt, jedoch können Templates jederzeit das standardmäßig vorhandene Ereignis ('any event') weiter einschränken, um spezifischen Anforderungen gerecht zu werden, wie z.B. der Messung zu bestimmten Zeitpunkten, oder über eine Anzahl von Intervallen (+/- mathematische Funktionen).">
			keywords = <"Beobachtungen", "Messungen", "Vitalparameter", "Mittlerer arterieller Druck", "Pulsdruck", "systolisch", "diastolisch", "RR", "Riva-Rocci", "NIBP">
			misuse = <"Nicht benutzen zur Dokumentation des intravenösen Drucks.
Nicht benutzen zur Dokumentation des arteriellen Blutdrucks, welcher KEIN Surrogat für den arteriellen Druck in der systemischen Zirkluation ist, z.B. die spezifische Messung des rechten pulmonaren Arteriendrucks.
In diesem Fall sollte der OBSERVATION.intravascular_pressure Archetyp bzw. dessen Spezialisierungen verwendet werden.">
			copyright = <"© openEHR Foundation">
		>
		["zh-cn"] = <
			language = <[ISO_639-1::zh-cn]>
			purpose = <"*To record the systemic blood pressure of a person. The measurement records the systolic and the diastolic pressure by some means suitable for the result to be seen as a surrogate for the general and systemic blood pressure.(en)">
			use = <"*All blood pressure measurements are recorded using this archetype. There is a rich state model for use with exercise ECGs and Tilt Table measurements.(en)">
			keywords = <"*observations(en)", "*blood pressure(en)", "*measurement(en)">
			misuse = <"*Not to be used for intravascular pressure.(en)">
			copyright = <"© openEHR Foundation">
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			purpose = <"Het registreren van de systemische arteriele bloeddruk van een individu.">
			use = <"Wordt gebruikt om alle weergaven van de systemische bloeddruk te registreren, ongeacht welke methode of welke lichaamslocatie is gebruikt om de meting te doen. Het archetype is bedoeld om bloeddruk metingen in alle klinische scenario's vast te leggen - bijvoorbeeld, zelf-meting met een thuis bloeddrukmeter; een nood beoordeling van de systolische bloeddruk met behulp van palpatie en een drukmanchet; metingen tijdens consulten, overleg of tijdens inspannings stress testen, en een reeks van metingen die door een apparaat zijn gedaan in de intensieve zorg.
Er is een uitgebreid status model dat interpretatie van metingen ondersteunt, door patiënt positie, inspanning, beïnvloedende factoren en de hoek/het aantal graden waarin de onderzoekstafel staat, te specificeren.
Genoemde gebeurtenissen zijn gelimiteerd tot een gemiddelde over een periode van 24 uur, maar templates kunnen de standaard 'iedere gebeurtenis' verder vernauwen om specifieke eisen voor de bloeddrukmeting, zoals registreren van de bloeddruk op een specifiek tijdsmoment, of over een reeks van intervallen (+/- statistisch gebruik) te faciliteren.
">
			keywords = <"observaties", "meting", "blddr", "vitale functies", "gemiddelde arteriele druk", "polsdruk", "systolisch", "diastolisch", "RR", "NIBP", "tensie">
			misuse = <"Niet te gebruiken voor intraveneuze druk.
Niet te gebruiken voor de meting van de arteriele bloeddruk welke geen surrogaat is voor de arteriele druk in de systemische circulatie, bv de specifieke meting van de rechter arterie pulmonalis druk.
Gebruik OBSERVATION.intravascular_pressure en gerelateerde specialisaties in beide situaties.">
			copyright = <"© openEHR Foundation">
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			purpose = <"Для записи системного артериального давления крови человека.">
			use = <"Используется для записи всех представлений измерения системного артериального  кровяного давления, независимо от используемого метода или расположения тела пациента. Архетип предназначен для записи измерений давления во всех клинических сценариях - например, самостоятельное измерение давления крови домашним автоматическим манометром, в чрезвычайной  ситуации использование  пальпации пульсовой волны и сфигмоманометр; измерений в ходе клинических консультаций или в ходе осуществления стресс-тестирования, а также серии измерений, выполненных аппаратом в реанимации.
Поддерживает интерпретацию измерений путем определения позиции пациента, физические упражнения, осложняющих факторов и угла наклона стола в научных исследованиях.
Предполаагется интервал между измерениями 24 часа, однако может быть дополнено событиями (по умолчанию \"любое событие\") для удовлетворения специфических требований для измерения кровяного давления, такие как записи в отношении кровяного давления конкретные моменты времени, или в диапазоне интервалов.">
			keywords = <"обследование", "измерение", "артериальное давление", "диастолическое", "систолическое">
			misuse = <"Не следует использовать для внутривенного давления.
Не следует использовать для измерения артериального давления, которое не является суррогатом артериального давления в системном кровотоке, например, конкретные измерения давления в легочной артерии.
Использовать OBSERVATION.intravascular_pressure и смежных специальностей в обоих этих ситуациях.
">
			copyright = <"© openEHR Foundation">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			purpose = <"ثبت نمودن فشار خون وریدی کل یک فرد">
			use = <"برای ثبت هر چیز نشاندهنده اندازه گیری فشاره خون وریدی کل، جدا از ابنکه برای ثبت آن از چه شیوه ای یا کدام بخش از بدن استفاده شده باشد، بکار می رود. این الگوساز برای گردآوری اندازه گیری فشار خون در همه سناریوهای بالینی طراحی شده است، مانند اندازه گیری توسط خود فرد بوسیله دستگاه فشار خون خانگی، ارزیابی اورژانسی سیستولیک با لمس نبض و یک \"فشارسنج خون\"، اندازه گیریهای انجام گرفته در مشاوره بالینی یا حین تست ورزشی، و یا یک رشته از اندازه گیریهای دستگاه مراقبت های ویژه.
مدل حالت توانمندی وجود دارد که تفسیر اندازه گیری ها را از طریق شناسایی موقعیت بیمار، ورزش، فاکتورهای مبهم و تست تخت شیبدار، پشتیبانی می کند.
رویدادهای نام گذاری شده بگونه ای محدود شده اند که روی یک دوره 24 ساعته میانگین گیری کنند هر چند که الگو ها می توانند پیش فرض -هر گونه  رویداد- را برای فراهم کردن خواسته های خاص از اندازه گیری فشار خون، با محدودیتهایی نظیر ثبت فشار خون سر وقت یا روی رنجی از فاصله های زمانی (با عمل جمع یا منها)، بیشتر محدود کنند 
">
			keywords = <"مشاهدات", "اندازه گیری", "فشار خون", "علایم حیاتی", "میانگین فشار وریدی", "فشار نبض", "سیستولیک", "دیاستولیک", "تنفسهای سریع", "فشار خون غیر تهاجمی">
			misuse = <"برای فشار داخل وریدی استفاده نشود.
برای اندازه گیری فشار خون وریدی نباید استفاده شود که جایگزینی برای فشار وریدی در گردش خون کلی نیست، بعنوان مثال اندازه گیری خاص فشار وریدی ریه راست.

 و تخصص های مربوطه برای موارد بالا بکار رود\"OBSERVATION.intravascular_pressure\"
 
">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"لتسجيل ضغط الدم الشرياني النظامي للشخص">
			use = <"يستخدم لتسجيل جميع طرق عرض ضغط الدم الشرايني النظامي, بغض النظر عن الطريقة أو الموضع من الجسم المستخدم في التسجيل.

يستخدم هذا النموذج لالتقاط قياسات ضغط الدم في جميع السيناريوهات السريرية - مثلا, قياس ضغط الدم بواسطة الشخص لنفسه باستخدام آلة القياس المنزلية, تقييم الضغط الانقباضي في حالة الطوارئ باستخدام المجس و مقياس الضغط الزئبقي, القياسات التي تم أخذها في الاستشارات السريرية أو في أثناء اختبار الضغط البدني, و سلسلة من القياسات التي تتم باستخدام آلات العناية المركزة.

يستخدم هذا النموذج الغني في تسجيل حالات القياس من خلال تفسيره في ضوء وضع المريض عند القياس, المجهود البدني, العوامل المربكة, و زاوية انحناء الطاولة المستخدمة عند القياس.

تم تحديد بعض الوقائع إلى المتوسط خلال 24 ساعة, إلا أن القوالب تستطيع تقييد الاختيار التلقائي (إحدى الوقائع) لمتطلبات معينة حول قياسات ضغط الدم مثل تسجيل ضغط الدم في نقاط زمنية معينة أو خلال مدى من الفواصل الزمنية - زائد أو ناقص دوال حسابية">
			keywords = <"الملاحظات", "القياس", "ضغط الدم", "العلامات الحياتية", "متوسط الضغط الشرياني", "الضغط عند النبض", "الانقباضي", "الانبساطي", "معدل التنفس", "قياس ضغط الدم غير الباضع">
			misuse = <"لا يستخدم لتسجيل الضغط داخل الوريد.
لا يستخدم لقياس ضغط الدم الشرياني الذي لا يحل بديلا عن ضغط الدم الشرياني في الدورة الجهازية مثل قياسات معينة لضغط الشريان الرئوي الأيمن.
استخدم نموذج ملاحظة. الضغط داخل الأوعية الدموية , و التخصيصات المتعلقة في كل من هذين الموقفين.">
			copyright = <"© openEHR Foundation">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			purpose = <"Registrar la presión arterial sistémica de un individuo">
			use = <"Usar para registrar todas las representaciones de la presión arterial sistémica, sin importar que método o localización del cuerpo se use para el registro. El arquetipo se usa para capturar la medida de la presión arterial en todos los escenarios clínicos - por ejemplo: automedición con un tensiómetro de uso domiciliario; la evaluación en situación de emergencia, de la sistólica usando palpación y un esfingomanómetro; medidas tomadas durante la consulta clínica o durante la prueba de esfuerzo (ergometría); y la serie de medidas automáticas hechas en la Unidad de Cuidados Intensivos.
Existe un variado modelo de situaciones que soporta la interpretación de mediciones a través de la interpretación de la posición del paciente, ejercicio, factores confluentes y el ángulo de inclinación de la camilla en situaciones de investigación.
Los eventos se han limitado a promediarse sobre un intervalo de 24 horas, sin embargo plantillas pueden acotar la medida por defecto 'cualquier evento' para ajustarse a requerimientos específicos de medida de la presión arterial como el Registro de la Tensión Arterial durante momentos específicos de tiempo, o sobre un rango de intervalos (+/- funciones matemáticas)

 ">
			keywords = <"observaciones(sp)", "mediciones(sp)", "presión arterial(sp)", "signos vitales(sp)", "presión arterial media(sp)", "presión pulso(sp)", "sistólica(sp)", "diastólica(sp)", "RR(en)", "Presión Arterial No Invasiva(sp)", "PANI(sp)">
			misuse = <"No debe usarse para la presión intravenosa
No debe usarse para la medida de la presión arterial que NO deriva de la presión arterial de la circulación sistémica ej: la medida específica de la presión de la arteria Pulmonar (presión capilar)
Usen Observación.presión_intravascular y especializaciones relacionadas para estas dos situaciones en particular.
">
			copyright = <"© openEHR Foundation">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			purpose = <"Para registrar a pressão arterial sistêmica de um indivíduo.">
			use = <"Usado para registrar todas as representações da medida da  pressão areterial sistêmica, não importando qual método ou localização corporal usada para registrá-la. O objetivo do arquétipo é capturar a pressão sanguínea em todos os cenários clínicos - por exemplo, auto-medida com um aparelho de pressão caseiro; um avaliação de emergência da pressão sistólica usando palpação e esfigmomanômetro; medidas realizadas em consultas clínicas ou durante testes de esforço; e uma série de medidas feitas por uma máquina em uma Unidade de Terapia Intensiva.
Existe um modelo rico que apoia a interpretação de medidas através da identificação da posição do paciente, nível exercício, gatores confundidores e ângulo de uma mesa de inclinação em uma pesquisa.
Eventos nomeados têm sido limitados em médica a um período de 24 horas, entretanto templates podem, posteriormente, restringir o padrão predeterminado 'qualquer evento'  para atender a requisitos específicos registro de medida de pressão sanguínea em pontos no tempo específicos, ou em faixas de intervalos (+/-funções matemáticas).">
			keywords = <"observações", "medidas", "PA", "pressão sanguínea", "sinais vitais", "Pressão arterial média", "Pressão de Pulso", "sistólica", "diástólica">
			misuse = <"Não deve ser usada para registrar pressão intravenosa.
Não deve ser usada para medida da pressão arterial que NÃO é um substituto da pressão arterial na circulação sistêmica, por exemplo, medida específica da pressão da artéria Pulmonar direita.
Em ambas situações use OBSERVATION.intravascular_pressure e especializações relacionadas.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Koray Atalag, University of Auckland, New Zealand", "Knut Bernstein, MEDIQ, Denmark", "Marja Buur, Medisch Centrum Alkmaar, Netherlands", "Rong Chen, Cambio Healthcare Systems, Sweden", "Beatriz de Faria Leão, Zilics, Brazil", "Paul Donaldson, Nursing Informatics Australia, Australia", "Jose Florez Arango, Universidad de Antioquia, Colombia", "Gerard Freriks, ERC, Netherlands", "Sebastian Garde, Ocean Informatics, Germany", "Anneke Goossen, Results 4 Care, Netherlands", "Sam Heard, Ocean Informatics, Australia", "Karsten Heusser, Hannover Medical School, Germany", "Omer Hotomaroglu, Turkey", "Evelyn Hovenga, EJSH Consulting, Australia", "Derek Hoy, United Kingdom", "Pieter Hummel, Medisch Centrum Alkmaar, Netherlands", "Eugene Igras, IRIS Systems, Inc., Canada", "Sundaresan Jagannathan, Scottish NHS, United Kingdom", "Andrew James, University of Toronto, Canada", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Rikard Lovstrom, Swedish Medical Association, Sweden", "Rohan Martin, Ambulance Victoria, Australia", "Ian McNicoll, Ocean Informatics, United Kingdom", "Jeroen Meintjens, Medisch Centrum Alkmaar, Netherlands", "Udo Müller-Oest, CompuGROUP Software, Germany", "Melvin Reynolds, United Kingdom", "Tony Shannon, NHS, United Kingdom", "Hwei-Yee Tai, Tan Tock Seng Hospital, Singapore", "Stef Verlinden, Vivici, Netherlands", "Soon Ghee Yap, Singapore Health Services Pte Ltd, Singapore">
	other_details = <
		["references"] = <"O'Brien E, Asmar R, Beilin L, et al. European Society of Hypertension recommendations for conventional, ambulatory and home blood pressure measurement. Journal of Hypertension [Internet]. 2003 [cited 2009 Jul 30] ; 21(5):821-848. Available from http://www.bhsoc.org/bp_monitors/ESH_BP_rec.pdf

Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Human blood pressure determination by sphygmomanometry. Circulation [Internet]. 1993 [cited 2009 Jul 29] 88 (5): 2460.  Available from: http://circ.ahajournals.org/cgi/reprint/88/5/2460
">
		["MD5-CAM-1.0.1"] = <"31406F8DDAF6C4DD73C174EE7C1B03C6">
	>

definition
	OBSERVATION[at0000] matches {	-- Blood Pressure
		data matches {
			HISTORY[at0001] matches {	-- history
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0006] occurrences matches {0..*} matches {	-- any event
						data matches {
							ITEM_TREE[at0003] matches {	-- blood pressure
								items cardinality matches {0..*; unordered} matches {
									ELEMENT[at0004] occurrences matches {0..1} matches {	-- Systolic
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::125]>
												list = <
													["1"] = <
														units = <"mm[Hg]">
														magnitude = <|0.0..<1000.0|>
														precision = <|0|>
													>
												>
											>
										}
									}
									ELEMENT[at0005] occurrences matches {0..1} matches {	-- Diastolic
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::125]>
												list = <
													["1"] = <
														units = <"mm[Hg]">
														magnitude = <|0.0..<1000.0|>
														precision = <|0|>
													>
												>
											>
										}
									}
									ELEMENT[at1006] occurrences matches {0..1} matches {	-- Mean Arterial Pressure
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::125]>
												list = <
													["1"] = <
														units = <"mm[Hg]">
														magnitude = <|0.0..<1000.0|>
														precision = <|0|>
													>
												>
											>
										}
									}
									ELEMENT[at1007] occurrences matches {0..1} matches {	-- Pulse Pressure
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::125]>
												list = <
													["1"] = <
														units = <"mm[Hg]">
														magnitude = <|0.0..<1000.0|>
														precision = <|0|>
													>
												>
											>
										}
									}
									ELEMENT[at0033] occurrences matches {0..1} matches {	-- Comment
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
						state matches {
							ITEM_TREE[at0007] matches {	-- state structure
								items cardinality matches {0..*; unordered} matches {
									ELEMENT[at0008] occurrences matches {0..1} matches {	-- Position
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at1000, 	-- Standing
													at1001, 	-- Sitting
													at1002, 	-- Reclining
													at1003, 	-- Lying
													at1014; 	-- Lying with tilt to left
													at1001]	-- assumed value
												}
											}
										}
									}
									ELEMENT[at1052] occurrences matches {0..1} matches {	-- Confounding factors
										value matches {
											DV_TEXT matches {*}
										}
									}
									allow_archetype CLUSTER[at1030] occurrences matches {0..1} matches {	-- Exertion  
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.level_of_exertion(-[a-zA-Z0-9_]+)*\.v1/}
									}
									ELEMENT[at1043] occurrences matches {0..1} matches {	-- Sleep status
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at1044, 	-- Alert & awake
													at1045; 	-- Sleeping
													at1044]	-- assumed value
												}
											}
										}
									}
									ELEMENT[at1005] occurrences matches {0..1} matches {	-- Tilt
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::497]>
												list = <
													["1"] = <
														units = <"°">
														magnitude = <|-90.0..90.0|>
														precision = <|0|>
													>
												>
												assumed_value = <
													magnitude = <0.0>
													units = <"°">
													precision = <0>
												>
											>
										}
									}
								}
							}
						}
					}
					INTERVAL_EVENT[at1042] occurrences matches {0..1} matches {	-- 24 hour average 
						math_function matches {
							DV_CODED_TEXT matches {
								defining_code matches {[openehr::146]}
							}
						}
						width matches {
							DV_DURATION matches {
								value matches {|PT24H|}
							}
						}
						data matches {
							use_node ITEM_TREE /data[at0001]/events[at0006]/data[at0003]	-- /data[history]/events[any event]/data[blood pressure]
						}
						state matches {
							use_node ITEM_TREE /data[at0001]/events[at0006]/state[at0007]	-- /data[history]/events[any event]/state[state structure]
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0011] matches {	-- list structure
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0013] occurrences matches {0..1} matches {	-- Cuff size
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0015, 	-- Adult Thigh
									at0016, 	-- Large Adult
									at0017, 	-- Adult
									at1008, 	-- Small Adult
									at1009, 	-- Paediatric/Child
									at1018, 	-- Infant
									at1019]	-- Neonatal
								}
							}
						}
					}
					CLUSTER[at1033] occurrences matches {0..1} matches {	-- Location
						items cardinality matches {1..*; unordered} matches {
							ELEMENT[at0014] occurrences matches {0..1} matches {	-- Location of measurement
								value matches {
									DV_CODED_TEXT matches {
										defining_code matches {
											[local::
											at0025, 	-- Right arm
											at0026, 	-- Left arm
											at0027, 	-- Right thigh
											at0028, 	-- Left thigh
											at1020, 	-- Right wrist
											at1021, 	-- Left wrist
											at1026, 	-- Right ankle
											at1031, 	-- Left ankle
											at1032, 	-- Finger
											at1051, 	-- Toe
											at1053]	-- Intra-arterial
										}
									}
								}
							}
							ELEMENT[at1034] occurrences matches {0..1} matches {	-- Specific location
								value matches {
									DV_TEXT matches {*}
								}
							}
						}
					}
					ELEMENT[at1035] occurrences matches {0..1} matches {	-- Method
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at1036, 	-- Auscultation
									at1037, 	-- Palpation
									at1039, 	-- Machine
									at1040]	-- Invasive
								}
							}
						}
					}
					ELEMENT[at1038] occurrences matches {0..1} matches {	-- Mean Arterial Pressure Formula
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at1010] occurrences matches {0..1} matches {	-- Diastolic endpoint
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at1011, 	-- Phase IV
									at1012]	-- Phase V
								}
							}
						}
					}
					allow_archetype CLUSTER[at1025] occurrences matches {0..1} matches {	-- Device
						include
							archetype_id/value matches {/openEHR-EHR-CLUSTER\.device(-[a-zA-Z0-9_]+)*\.v1/}
					}
				}
			}
		}
	}


ontology
	terminologies_available = <"SNOMED-CT", ...>
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Blood Pressure">
					description = <"The local measurement of arterial blood pressure which is a surrogate for arterial. pressure in the systemic circulation.  Most commonly, use of the term 'blood pressure' refers to measurement of brachial artery pressure in the upper arm.">
				>
				["at0001"] = <
					text = <"history">
					description = <"history Structural node">
				>
				["at0003"] = <
					text = <"blood pressure">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Systolic">
					description = <"Peak systemic arterial blood pressure  - measured in systolic or contraction phase of the heart cycle.">
				>
				["at0005"] = <
					text = <"Diastolic">
					description = <"Minimum systemic arterial blood pressure - measured in the diastolic or relaxation phase of the heart cycle.">
				>
				["at0006"] = <
					text = <"any event">
					description = <"Default event">
				>
				["at0007"] = <
					text = <"state structure">
					description = <"@ internal @">
				>
				["at0008"] = <
					text = <"Position">
					description = <"The position of the subject at the time of measurement.">
				>
				["at0011"] = <
					text = <"list structure">
					description = <"list structure">
				>
				["at0013"] = <
					text = <"Cuff size">
					description = <"The size of the cuff used for blood pressure measurement.  ">
					comment = <"Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Human blood pressure determination by sphygmomanometry. Circulation 1993;88;2460-2470. ">
				>
				["at0014"] = <
					text = <"Location of measurement">
					description = <"Common body sites where blood pressure is recorded.">
				>
				["at0015"] = <
					text = <"Adult Thigh">
					description = <"A cuff used for an adult thigh - bladder approx 20cm x 42cm.">
				>
				["at0016"] = <
					text = <"Large Adult">
					description = <"A cuff for adults with larger arms - bladder approx 16cm x 38cm.">
				>
				["at0017"] = <
					text = <"Adult">
					description = <"A cuff that is standard for an adult - bladder approx 13cm x 30cm.">
				>
				["at0025"] = <
					text = <"Right arm">
					description = <"The right arm of the person.">
				>
				["at0026"] = <
					text = <"Left arm">
					description = <"The left arm of the person.">
				>
				["at0027"] = <
					text = <"Right thigh">
					description = <"The right thigh of the person.">
				>
				["at0028"] = <
					text = <"Left thigh">
					description = <"The left thigh of the person.">
				>
				["at0033"] = <
					text = <"Comment">
					description = <"Comment on blood pressure measurement.">
				>
				["at1000"] = <
					text = <"Standing">
					description = <"Standing at the time of blood pressure measurement.">
				>
				["at1001"] = <
					text = <"Sitting">
					description = <"Sitting (for example on bed or chair) at the time of blood pressure measurement.">
				>
				["at1002"] = <
					text = <"Reclining">
					description = <"Reclining at the time of blood pressure measurement.">
				>
				["at1003"] = <
					text = <"Lying">
					description = <"Lying flat at the time of blood pressure measurement.">
				>
				["at1005"] = <
					text = <"Tilt">
					description = <"The craniocaudal tilt of the surface on which the person is lying at the time of measurement.">
				>
				["at1006"] = <
					text = <"Mean Arterial Pressure">
					description = <"The average arterial pressure that occurs over the entire course of the heart contraction and relaxation cycle.">
				>
				["at1007"] = <
					text = <"Pulse Pressure">
					description = <"The difference between the systolic and diastolic pressure.">
				>
				["at1008"] = <
					text = <"Small Adult">
					description = <"A cuff used for a small adult - bladder approx 10cm x 24cm.">
				>
				["at1009"] = <
					text = <"Paediatric/Child">
					description = <"A cuff that is appropriate for a child or adult with a thin arm - bladder approx 8cm x 21cm.">
				>
				["at1010"] = <
					text = <"Diastolic endpoint">
					description = <"Record which Korotkoff sound is used for determining diastolic pressure using auscultative method.">
				>
				["at1011"] = <
					text = <"Phase IV">
					description = <"The fourth Korotkoff sound is identified as an abrupt muffling of sounds.">
				>
				["at1012"] = <
					text = <"Phase V">
					description = <"The fifth Korotkoff sound is identified by absence of sounds as the cuff pressure drops below the diastolic blood pressure.">
				>
				["at1014"] = <
					text = <"Lying with tilt to left">
					description = <"Lying flat with some lateral tilt, usually angled towards the left side.   Commonly required in the last trimester of pregnancy to relieve aortocaval compression.">
				>
				["at1018"] = <
					text = <"Infant">
					description = <"A cuff used for infants - bladder approx 5cm x 15cm.">
				>
				["at1019"] = <
					text = <"Neonatal">
					description = <"A cuff used for a neonate, assuming cuff is the appropriate size for maturity and birthweight of the neonate.">
				>
				["at1020"] = <
					text = <"Right wrist">
					description = <"The right wrist of the subject.">
				>
				["at1021"] = <
					text = <"Left wrist">
					description = <"The left wrist of the subject.">
				>
				["at1025"] = <
					text = <"Device">
					description = <"Details about sphygmomanometer or other device used to measure the blood pressure.">
				>
				["at1026"] = <
					text = <"Right ankle">
					description = <"The right ankle of the subject.">
				>
				["at1030"] = <
					text = <"Exertion  ">
					description = <"Details about physical activity undertaken at the time of blood pressure.measurement.">
				>
				["at1031"] = <
					text = <"Left ankle">
					description = <"The left ankle of the subject.">
				>
				["at1032"] = <
					text = <"Finger">
					description = <"A finger of the subject.  Identification of the finger can be recorded in 'Specific Location' data element, if required.">
				>
				["at1033"] = <
					text = <"Location">
					description = <"Body location where blood pressure is measured.  Use 'Location of measurement' to select from common sites.  Use 'Specific location' to record more specific details or a site that is not in the common set or to refer to an external terminology.">
				>
				["at1034"] = <
					text = <"Specific location">
					description = <"Specific details about the body site where blood pressure is recorded.">
				>
				["at1035"] = <
					text = <"Method">
					description = <"Method of measurement of blood pressure.">
				>
				["at1036"] = <
					text = <"Auscultation">
					description = <"Method of measuring blood pressure externally, using a stethoscope and Korotkoff sounds.">
				>
				["at1037"] = <
					text = <"Palpation">
					description = <"Method of measuring blood pressure externally, using palpation (usually of the brachial or radial arteries).">
				>
				["at1038"] = <
					text = <"Mean Arterial Pressure Formula">
					description = <"Formula used to calculate the MAP (if recorded in data).">
				>
				["at1039"] = <
					text = <"Machine">
					description = <"Method of measuring blood pressure externally, using a blood pressure machine.">
				>
				["at1040"] = <
					text = <"Invasive">
					description = <"Method of measuring blood pressure internally ie involving penetration of the skin and measuring inside blood vessels.">
				>
				["at1042"] = <
					text = <"24 hour average ">
					description = <"Estimate of the average blood pressure over a 24 hour period.">
				>
				["at1043"] = <
					text = <"Sleep status">
					description = <"Sleep status - supports interpretation of 24 hour ambulatory blood pressure records. ">
				>
				["at1044"] = <
					text = <"Alert & awake">
					description = <"Subject is fully conscious.">
				>
				["at1045"] = <
					text = <"Sleeping">
					description = <"Subject is in the natural state of bodily rest.">
				>
				["at1051"] = <
					text = <"Toe">
					description = <"A toe of the subject.   Identification of the toe can be recorded in 'Specific Location' data element, if required.">
				>
				["at1052"] = <
					text = <"Confounding factors">
					description = <"Comment on and record other incidental factors that may be contributing to the blood pressure measurement.  For example, level of anxiety or 'white coat syndrome'; pain or fever; changes in atmospheric pressure etc.">
				>
				["at1053"] = <
					text = <"Intra-arterial">
					description = <"Invasive measurement via transducer access line within an artery. Location of the transducer can be recorded in 'Specific Location' data element, if required.">
				>
			>
		>
		["ja"] = <
			items = <
				["at0000"] = <
					text = <"血圧">
					description = <"全身の循環での動脈圧の代用として，局所で測定される血圧。一般的には「血圧」とは上腕で上腕動脈を測定したものをさすことが多い。">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*history Structural node(en)">
				>
				["at0003"] = <
					text = <"血圧">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"収縮期">
					description = <"1つ以上の脈の間で最高値を示す全身の動脈圧 - 心機図の収縮期で測定される">
				>
				["at0005"] = <
					text = <"拡張期">
					description = <"1つ以上の脈の間で最低値を示す全身の動脈圧 - 心機図の拡張期で測定される">
				>
				["at0006"] = <
					text = <"血圧">
					description = <"*Default event(en)">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"体位">
					description = <"計測のときの対象者の体位">
				>
				["at0011"] = <
					text = <"*list structure(en)">
					description = <"*list structure(en)">
				>
				["at0013"] = <
					text = <"カフサイズ">
					description = <"血圧測定のために使われるカフの大きさ.">
					comment = <"Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Human blood pressure determination by sphygmomanometry. Circulation 1993;88;2460-2470.">
				>
				["at0014"] = <
					text = <"計測部位">
					description = <"血圧が一般的に測定される身体の部位">
				>
				["at0015"] = <
					text = <"成人大腿">
					description = <"成人の大腿で血圧を測定するためのカフ。袋はおよそ 20cm x 42cm.">
				>
				["at0016"] = <
					text = <"大柄な成人">
					description = <"大柄な成人のためのカフ 袋はおよそ 16cm x 38cm.">
				>
				["at0017"] = <
					text = <"成人">
					description = <"一般的な成人のためのカフ - 袋はおよそ 13cm x 30cm.">
				>
				["at0025"] = <
					text = <"右腕">
					description = <"*The right arm of the person(en)">
				>
				["at0026"] = <
					text = <"左腕">
					description = <"*The left arm of the person(en)">
				>
				["at0027"] = <
					text = <"右足">
					description = <"*The right leg of the person(en)">
				>
				["at0028"] = <
					text = <"左脚">
					description = <"*The left leg of the person(en)">
				>
				["at0033"] = <
					text = <"コメント">
					description = <"血圧測定のコメント">
				>
				["at1000"] = <
					text = <"立位">
					description = <"*Standing at the time of blood pressure measurement(en)">
				>
				["at1001"] = <
					text = <"座位">
					description = <"*Sitting on bed or chair at the time of blood pressure measurement(en)">
				>
				["at1002"] = <
					text = <"斜位">
					description = <"*Person reclining at 45 degrees at the time of blood pressure measurement(en)">
				>
				["at1003"] = <
					text = <"臥位">
					description = <"臥位での測定血圧">
				>
				["at1005"] = <
					text = <"ティルト">
					description = <"*The craniocaudal tilt of the surface on which the person is lying at the time of measurement(en)">
				>
				["at1006"] = <
					text = <"平均同脈圧">
					description = <"縮拡張サイクルのすべての過程における動脈圧の平均値.">
				>
				["at1007"] = <
					text = <"脈圧">
					description = <"1回の収縮サイクルでの血圧の変動">
				>
				["at1008"] = <
					text = <"小柄な成人">
					description = <"小柄な成人のためのカフ - 袋はおよそ 10cm x 24cm.">
				>
				["at1009"] = <
					text = <"幼児/省に">
					description = <"小児あるいは痩せた成人のためのカフ - 袋はおよそ 8cm x 21cm.">
				>
				["at1010"] = <
					text = <"拡張期終末">
					description = <"拡張期圧を決めるためにどのコロトコフ音が使用されたかというを記録.">
				>
				["at1011"] = <
					text = <"4期">
					description = <"コロトコフの4音。急速に減弱する時期.">
				>
				["at1012"] = <
					text = <"5期">
					description = <"コロトコフの5音が聴取される時期。カフ圧が拡張期圧を下回り音が聴取されなくなる時期">
				>
				["at1014"] = <
					text = <"左側臥位">
					description = <"側臥位　通常は左側　通常は妊娠最終トリメスタで必要となる体位">
				>
				["at1018"] = <
					text = <"幼児">
					description = <"幼児のために使われるカフ - 袋はおよそ 5cm x 15cm.">
				>
				["at1019"] = <
					text = <"新生児">
					description = <"新生児用のカフ 想定されるカフは生下時体重と成熟度に応じて適切なものであること.">
				>
				["at1020"] = <
					text = <"右手首">
					description = <"対象の右手首">
				>
				["at1021"] = <
					text = <"左手首">
					description = <"対象の左手首">
				>
				["at1025"] = <
					text = <"測定機器">
					description = <"水銀血圧計あるいはそのほかの血圧を測定するために使われる機器.">
				>
				["at1026"] = <
					text = <"右足首">
					description = <"対象の右足首">
				>
				["at1030"] = <
					text = <"労作">
					description = <"*Details about physical activity undertaken at the time of blood pressure measurement(en)">
				>
				["at1031"] = <
					text = <"左足首">
					description = <"対象の左足首">
				>
				["at1032"] = <
					text = <"指">
					description = <"対象の指。指の識別は必要であれば｢特別な部位」エレメントで記録される">
				>
				["at1033"] = <
					text = <"部位">
					description = <"*Body location where blood pressure is measured.  Use 'Location of measurement' to select from common sites.  Use 'Specific location' to record more specific details or a site that is not in the common set or to refer to an external terminology. (en)">
				>
				["at1034"] = <
					text = <"特別な部位">
					description = <"血圧が測定される場所についての詳細な記録.">
				>
				["at1035"] = <
					text = <"方法">
					description = <"*Method of measurement of blood pressure.(en)">
				>
				["at1036"] = <
					text = <"聴診">
					description = <"聴診器を使いコロトコフ音で外部から血圧を測定する方法.">
				>
				["at1037"] = <
					text = <"触診">
					description = <"脈拍(通常は上腕動脈あるいは橈骨動脈）を触診することにより外部から血圧を測定する方法">
				>
				["at1038"] = <
					text = <"平均同脈圧の計算式">
					description = <"平均同脈圧を計算するために使われた士気（もしデータに記録されていれば）">
				>
				["at1039"] = <
					text = <"機械">
					description = <"血圧測定器を使って外部から血圧を測定する方法.">
				>
				["at1040"] = <
					text = <"侵襲的">
					description = <"径皮的に動脈を穿刺し，血管内部から血圧を測定する方法.">
				>
				["at1042"] = <
					text = <"24時間平均">
					description = <"24時間にわたる推定平均血圧">
				>
				["at1043"] = <
					text = <"睡眠状況">
					description = <"睡眠状況 24時間外来血圧記録の解釈を助けるため">
				>
				["at1044"] = <
					text = <"覚醒">
					description = <"対象は常に意識がある">
				>
				["at1045"] = <
					text = <"睡眠中">
					description = <"対象は自然な休養状態にある">
				>
				["at1051"] = <
					text = <"足先">
					description = <"対象の足尖部。足尖部の識別は必要であれば「特別な部位」エレメントに記録される">
				>
				["at1052"] = <
					text = <"交絡因子">
					description = <"*Comment on and record other incidental factors that may be contributing to the blood pressure measurement.  For example, level of anxiety or 'white coat syndrome'; pain or fever; changes in atmospheric pressure etc.(en)">
				>
				["at1053"] = <
					text = <"動脈内">
					description = <"動脈内のトランスデューサーに接続されたラインから侵襲的に測定する方法。動脈の部位は必要であれば「特別な部位」エレメントに記録される">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"Blutdruck">
					description = <"Die lokale Messung des arteriellen Blutdrucks als Surrogat für den arteriellen Druck in der systemischen Zirkulation. Häufig wird der Ausdruck 'Blutdruck' zur Bezeichung der Messung des brachialen Ateriendrucks im Oberarm verwendet.">
				>
				["at0001"] = <
					text = <"Historie">
					description = <"Historie">
				>
				["at0003"] = <
					text = <"Blutdruck">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Systolisch">
					description = <"Der höchste arterielle Blutdruck eines Zyklus - gemessen in der systolischen oder Kontraktionsphase des Herzens.">
				>
				["at0005"] = <
					text = <"Diastolisch">
					description = <"Der minimale systemische arterielle Blutdruck eines Zyklus - gemessen in der diastolischen oder Entspannungsphase des Herzens.">
				>
				["at0006"] = <
					text = <"any event">
					description = <"Default event">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"Position">
					description = <"Die Position der untersuchten Person während der Messung.">
				>
				["at0011"] = <
					text = <"Listenstruktur">
					description = <"Listenstruktur">
				>
				["at0013"] = <
					text = <"Manschettengröße">
					description = <"Die Größe der Manschette, die zur Blutdruckmessung benutzt wurde.">
					comment = <"Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Human blood pressure determination by sphygmomanometry. Circulation 1993;88;2460-2470.">
				>
				["at0014"] = <
					text = <"Körperstelle der Messung">
					description = <"Gewöhnliche Körperstellen, an denen der Blutdruck gemessen wird.">
				>
				["at0015"] = <
					text = <"Oberschenkel eines Erwachsenen">
					description = <"Eine Manschette für den Oberschenkel eines Erwachsenen - ca. 20cm x 42cm.">
				>
				["at0016"] = <
					text = <"Großer Erwachsener">
					description = <"Eine Manschette für Erwachsene mit größeren Armen - ca. 16cm x 38cm.">
				>
				["at0017"] = <
					text = <"Erwachsener">
					description = <"Eine Standard-Manschette für einen Erwachsenen - ca. 13cm x 30cm.">
				>
				["at0025"] = <
					text = <"Rechter Arm">
					description = <"Der rechte Arm der Person.">
				>
				["at0026"] = <
					text = <"Linker Arm">
					description = <"Der linke Arm der Person.">
				>
				["at0027"] = <
					text = <"Rechter Oberschenkel">
					description = <"Der rechte Oberschenkel der Person.">
				>
				["at0028"] = <
					text = <"Linker Oberschenkel">
					description = <"Der linke Oberschenkel der Person.">
				>
				["at0033"] = <
					text = <"Kommentar">
					description = <"Kommentar zur Blutdruckmessung.">
				>
				["at1000"] = <
					text = <"Stehend">
					description = <"Stehend zum Zeitpunkt der Blutdruckmessung.">
				>
				["at1001"] = <
					text = <"Sitzend">
					description = <"Sitzend zum Zeitpunkt der Blutdruckmessung (z.B. auf einem Bett oder Stuhl).">
				>
				["at1002"] = <
					text = <"Zurückgelehnt">
					description = <"Patient zurückgelehnt zum Zeitpunkt der Blutdruckmessung.">
				>
				["at1003"] = <
					text = <"Liegend">
					description = <"Flach liegend zum Zeitpunkt der Blutdruckmessung.">
				>
				["at1005"] = <
					text = <"Neigung">
					description = <"Die cranio-kaudale Neigung der Oberfläche auf der die Person zum Zeitpunkt der Messung liegt.">
				>
				["at1006"] = <
					text = <"Mittlerer arterieller Druck">
					description = <"Der mittlerer arterielle Druck über den gesamten Verlauf der Konktraktions- und Entspannungsphase des Herzens.">
				>
				["at1007"] = <
					text = <"Pulsdruck">
					description = <"Der Abstand zwischen dem systolischen und dem diastolischen Blutdruckwert.">
				>
				["at1008"] = <
					text = <"Kleiner Erwachsener">
					description = <"Eine Manschette für einen kleinen Erwachsenen - ca. 10cm x 24cm.">
				>
				["at1009"] = <
					text = <"Pädiatrisch/Kind">
					description = <"Eine Manschette für ein Kind oder auch einen Erwachsenen mit einem schmalen Arm - 8cm x 21cm.">
				>
				["at1010"] = <
					text = <"Diastolischer Endpunkt">
					description = <"Dient der Dokumentation des Korotkoff-Geräusches, das verwendet wird, um bei auskultarischer Messung den diastolischen Blutdruck zu bestimmen.">
				>
				["at1011"] = <
					text = <"Phase IV">
					description = <"Das 4. Korotkoff-Geräusch - Die Geräusche klingen plätzlich gedämpft.">
				>
				["at1012"] = <
					text = <"Phase V">
					description = <"Das 5. Korotkoff-Geräusch - die Geräusche verschwinden völlig während der Manschettendruck unter den diastolischen Blutdruck fällt.">
				>
				["at1014"] = <
					text = <"Nach links geneigt liegend">
					description = <"Flach liegend mit seitlicher Neigung, normalerweise zur linken Seite. Häufig verwendet im letzten Drittel eine Schwangerschaft, um aorto-cavale Kompression zu vermeiden.">
				>
				["at1018"] = <
					text = <"Kleinkind">
					description = <"Eine Manschette für Kleinkinder und Säuglinge - ca. 5cm x 15cm.">
				>
				["at1019"] = <
					text = <"Neonatal">
					description = <"Eine Manschette für Neugeborene mit passender Größe für die Reife und das Geburtsgewicht des Neugeborenen.">
				>
				["at1020"] = <
					text = <"Rechtes Handgelenk">
					description = <"Das rechte Handgelenk der Person.">
				>
				["at1021"] = <
					text = <"Linkes Handgelenk">
					description = <"Das linke Handgelenk der Person.">
				>
				["at1025"] = <
					text = <"Gerät">
					description = <"Details über das Sphygmomanometer oder ein anderes Gerät, dass zur Blutdruckmessung verwendet wird.">
				>
				["at1026"] = <
					text = <"Rechtes Fußgelenk">
					description = <"Das rechte Fußgelenk der Person.">
				>
				["at1030"] = <
					text = <"Anstrengung">
					description = <"Details über physische Aktivitäten zur Zeit der Blutdruckmessung.">
				>
				["at1031"] = <
					text = <"Linkes Fußgelenk">
					description = <"Das linke Fußgelenk der Person">
				>
				["at1032"] = <
					text = <"Finger">
					description = <"Ein Finger der Person. Der Finger kann, falls benötigt, als 'Spezifische Stelle' genauer identifiziert werden.">
				>
				["at1033"] = <
					text = <"Körperstelle">
					description = <"Körperstelle der Blutdruckmessung. 'Körperstelle der Messung' kann für die gewöhnlichen Stellen verwendet werden. 'Spezifische Stelle' wird für die Aufzeichnung spezifischer Details einer Körperstelle, die nicht in den gewöhnlichen Stellen enthalten ist, verwendet, Sie kann auch verwendet werden, um auf eine externe Teminologie zu verweisen.">
				>
				["at1034"] = <
					text = <"Spezifische Stelle">
					description = <"Spezifische Details über die Körperstelle, an der der Blutdruck gemessen wird.">
				>
				["at1035"] = <
					text = <"Methode">
					description = <"Methode der Messung des Blutdrucks.">
				>
				["at1036"] = <
					text = <"Auskultation">
					description = <"Auskulatorische Messung unter Benutzung eines Stethoskops und der Korotkoff-Geräusche.">
				>
				["at1037"] = <
					text = <"Palpation">
					description = <"Palpatorische Messung, normalerweise an den brachialen oder radialen Arterien.">
				>
				["at1038"] = <
					text = <"Formel für mittleren arterieller Druck">
					description = <"Die Formel die ggf. verwendet wurde, um den mittleren arteriellen Druck zu berechnen.">
				>
				["at1039"] = <
					text = <"Machine">
					description = <"Messung durch eine Blutdruckmaschine.">
				>
				["at1040"] = <
					text = <"Invasiv">
					description = <"Invasive Messung des Blutdrucks innerhalb eines Gefäßes.">
				>
				["at1042"] = <
					text = <"24 Stunden Durchschnitt">
					description = <"Schätzung des durchschnittlichen Blutdrucks über eine 24-stündigen Zeitraum.">
				>
				["at1043"] = <
					text = <"Schlafzustand">
					description = <"Schlafzustand  - unterstützt die Auswertung von 24-stündigen ambulanten Aufzeichnungen des Blutdrucks.">
				>
				["at1044"] = <
					text = <"Aufmerksam und wach">
					description = <"Die untersuchte Person ist bei vollem Bewusstsein.">
				>
				["at1045"] = <
					text = <"Schlafend">
					description = <"Die untersuchte Person schläft.">
				>
				["at1051"] = <
					text = <"Zeh">
					description = <"Ein Zeh der Person. Der Zeh kann, falls benötigt, als 'Spezifische Stelle' genauer identifiziert werden.">
				>
				["at1052"] = <
					text = <"Einflussfaktoren">
					description = <"Kommentar und Aufzeichung anderer Faktoren die ggf. zu dem Ergebnis der Blutdruckmessung beitragen können. Die kann z.B. bei belastenden Situationen der Fall sein (z.B. sog. Weißkittelhypertonie, Schmerzen, Fieber, Änderungen im atmosphärischen Druck).">
				>
				["at1053"] = <
					text = <"Intra-arteriell">
					description = <"Invasive Messung über einen arteriellen Drucksensor. Die genaue Stelle des Drucksensors kann, falls benötigt, als 'Spezifische Stelle' genauer identifiziert werden.">
				>
			>
		>
		["zh-cn"] = <
			items = <
				["at0000"] = <
					text = <"*Blood Pressure(en)">
					description = <"*The local measurement of arterial blood pressure which is a surrogate for arterial pressure in the systemic circulation.  Most commonly, use of the term 'blood pressure' refers to measurement of brachial artery pressure in the upper arm.(en)">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*history Structural node(en)">
				>
				["at0003"] = <
					text = <"血压">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"收缩压">
					description = <"一个血液循环周期中，系统性动脉血压高峰值。 收缩期血压">
				>
				["at0005"] = <
					text = <"舒张压">
					description = <"一个血液循环周期中，系统性动脉血压最低值。 舒张期血压">
				>
				["at0006"] = <
					text = <"*any event(en)">
					description = <"*Default event(en)">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"*Position(en)">
					description = <"*The position of the subject at the time of measurement(en)">
				>
				["at0011"] = <
					text = <"*list structure(en)">
					description = <"*list structure(en)">
				>
				["at0013"] = <
					text = <"*Cuff size(en)">
					description = <"*The size of the cuff used for blood pressure measurement(en)">
					comment = <"*Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Human blood pressure determination by sphygmomanometry. Circulation 1993;88;2460-2470. (en)">
				>
				["at0014"] = <
					text = <"*Location of measurement(en)">
					description = <"*Common body locations where blood pressure is recorded(en)">
				>
				["at0015"] = <
					text = <"*Adult Thigh(en)">
					description = <"*A cuff used for an adult thigh - bladder approx 20cm x 42cm(en)">
				>
				["at0016"] = <
					text = <"*Large Adult(en)">
					description = <"*A cuff for adults with larger arms - bladder approx 16cm x 38cm(en)">
				>
				["at0017"] = <
					text = <"*Adult(en)">
					description = <"*A cuff that is standard for an adult - bladder approx 13cm x 30cm(en)">
				>
				["at0025"] = <
					text = <"右臂">
					description = <"被测试者右臂">
				>
				["at0026"] = <
					text = <"左臂">
					description = <"被测试者左臂">
				>
				["at0027"] = <
					text = <"*Right leg(en)">
					description = <"*The right leg of the person(en)">
				>
				["at0028"] = <
					text = <"左腿">
					description = <"被测试者左下肢">
				>
				["at0033"] = <
					text = <"注释">
					description = <"有关血压值的注释">
				>
				["at1000"] = <
					text = <"立位">
					description = <"测量血压时身体处于站立体位">
				>
				["at1001"] = <
					text = <"坐位">
					description = <"测量血压时身体处于坐位">
				>
				["at1002"] = <
					text = <"侧卧位">
					description = <"测量血压时身体处于45度角侧卧位">
				>
				["at1003"] = <
					text = <"*Lying(en)">
					description = <"*Lying flat at the time of blood pressure measurement.(en)">
				>
				["at1005"] = <
					text = <"*Tilt(en)">
					description = <"*The craniocaudal tilt of the surface on which the person is lying at the time of measurement(en)">
				>
				["at1006"] = <
					text = <"*Mean Arterial Pressure(en)">
					description = <"*The average arterial pressure that occurs over the entire course of the heart contraction and relaxation cycle.   (en)">
				>
				["at1007"] = <
					text = <"脉压">
					description = <"*The variation in pressure over one contraction cycle(en)">
				>
				["at1008"] = <
					text = <"*Small Adult(en)">
					description = <"*A cuff used for a small adult - bladder approx 10cm x 24cm(en)">
				>
				["at1009"] = <
					text = <"*Paediatric/Child(en)">
					description = <"*A cuff that is appropriate for a child or adult with a thin arm - bladder approx 8cm x 21cm.(en)">
				>
				["at1010"] = <
					text = <"*Diastolic endpoint(en)">
					description = <"*Record which Korotkoff sound is used for determining diastolic pressure using auscultative method(en)">
				>
				["at1011"] = <
					text = <"*Phase IV(en)">
					description = <"*The fourth Korotkoff sound is identified as an abrupt muffling of sounds(en)">
				>
				["at1012"] = <
					text = <"*Phase V(en)">
					description = <"*The fifth Korotkoff sound is identified by absence of sounds as the cuff pressure drops below the diastolic blood pressure(en)">
				>
				["at1014"] = <
					text = <"*Lying with tilt to left(en)">
					description = <"*Lying flat with some lateral tilt, usually angled towards the left side.   Commonly required in the last trimester of pregnancy to relieve aortocaval compression.(en)">
				>
				["at1018"] = <
					text = <"*Infant(en)">
					description = <"*A cuff used for infants - bladder approx 5cm x 15cm(en)">
				>
				["at1019"] = <
					text = <"*Neonatal(en)">
					description = <"*A cuff used for a neonate, assuming cuff is the appropriate size for maturity and birthweight of the neonate(en)">
				>
				["at1020"] = <
					text = <"*Right wrist(en)">
					description = <"*The right wrist of the subject(en)">
				>
				["at1021"] = <
					text = <"*Left wrist(en)">
					description = <"*The left wrist of the subject(en)">
				>
				["at1025"] = <
					text = <"*Device(en)">
					description = <"*Details about sphygmomanometer or other device used to measure the blood pressure(en)">
				>
				["at1026"] = <
					text = <"*Right ankle(en)">
					description = <"*The right ankle of the subject(en)">
				>
				["at1030"] = <
					text = <"*Exertion  (en)">
					description = <"*Details about physical activity undertaken at the time of blood pressure measurement(en)">
				>
				["at1031"] = <
					text = <"*Left ankle(en)">
					description = <"*The left ankle of the subject(en)">
				>
				["at1032"] = <
					text = <"*Finger(en)">
					description = <"*A finger of the subject.  Identification of the finger can be recorded in 'Specific Location' data element, if required.(en)">
				>
				["at1033"] = <
					text = <"*New cluster(en)">
					description = <"**(en)">
				>
				["at1034"] = <
					text = <"*Specific location(en)">
					description = <"*Detailed description about the site of the measurement of the blood pressure(en)">
				>
				["at1035"] = <
					text = <"*New element(en)">
					description = <"**(en)">
				>
				["at1036"] = <
					text = <"*Auscultation(en)">
					description = <"*Method of measuring blood pressure externally, using a stethoscope and Korotkoff sounds(en)">
				>
				["at1037"] = <
					text = <"*Palpation(en)">
					description = <"*Method of measuring blood pressure externally, using palpation (usually of the brachial or radial arteries)(en)">
				>
				["at1038"] = <
					text = <"*Mean Arterial Pressure Formula(en)">
					description = <"*Formula used to calculate the MAP (if recorded in data)(en)">
				>
				["at1039"] = <
					text = <"*Machine(en)">
					description = <"*Method of measuring blood pressure externally, using a blood pressure machine(en)">
				>
				["at1040"] = <
					text = <"*Invasive(en)">
					description = <"*Method of measuring blood pressure internally ie involving penetration of the skin and measuring inside blood vessels(en)">
				>
				["at1042"] = <
					text = <"*24 hour average (en)">
					description = <"*Estimate of the average blood pressure over a 24 hour period(en)">
				>
				["at1043"] = <
					text = <"*Sleep status(en)">
					description = <"*Sleep status - supports interpretation of 24 hour ambulatory blood pressure records. (en)">
				>
				["at1044"] = <
					text = <"*Alert & awake(en)">
					description = <"*Subject is fully conscious(en)">
				>
				["at1045"] = <
					text = <"*Sleeping(en)">
					description = <"*Subject is in the natural state of bodily rest(en)">
				>
				["at1051"] = <
					text = <"*Toe(en)">
					description = <"*A toe of the subject.   Identification of the toe can be recorded in 'Specific Location' data element, if required.(en)">
				>
				["at1052"] = <
					text = <"*Confounding factors(en)">
					description = <"*Comment on and record other incidental factors that may be contributing to the blood pressure measurement.  For example, level of anxiety or 'white coat syndrome'; pain or fever; changes in atmospheric pressure etc.(en)">
				>
				["at1053"] = <
					text = <"*Intra-arterial(en)">
					description = <"*Invasive measurement via transducer access line within an artery. Location of the transducer can be recorded in 'Specific Location' data element, if required.(en)">
				>
			>
		>
		["nl"] = <
			items = <
				["at0000"] = <
					text = <"Bloeddruk">
					description = <"De lokale meting van de arteriële bloeddruk, welke surrogaat is voor de arteriële druk in de systemische circulatie. Meest gebruikelijk is dat de term 'bloeddruk'  refereert aan de meting van de bloeddruk van de arterie brachialis in de bovenarm.">
				>
				["at0001"] = <
					text = <"Geschiedenis">
					description = <"Gestructureerde geschiedenismap">
				>
				["at0003"] = <
					text = <"*blood pressure(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Systole">
					description = <"De maximale (piek) systemische arteriele bloeddruk - gemeten in de systolische of samentrekkingsfase van de hartslag">
				>
				["at0005"] = <
					text = <"Diastole">
					description = <"Laagste systemische arteriele bloeddruk -  gemeten in de diastolische of ontspanningsfase van de hartslag">
				>
				["at0006"] = <
					text = <"any event">
					description = <"Default gebeurtenis">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"Houding">
					description = <"De houding van het individu op het moment van de meting">
				>
				["at0011"] = <
					text = <"lijst structuur">
					description = <"lijst structuur">
				>
				["at0013"] = <
					text = <"Manchet grootte">
					description = <"De grootte van de manchet gebruikt bij de meting">
					comment = <"Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Human blood pressure determination by sphygmomanometry. Circulation 1993;88;2460-2470. ">
				>
				["at0014"] = <
					text = <"Plaats van meting">
					description = <"Gewoonlijke lichaamslocaties waar bloeddruk gemeten wordt.">
				>
				["at0015"] = <
					text = <"Volwassen dijbeen">
					description = <"Een manchet voor een volwassen dijbeen - manchet grootte ca. 20cm x 42cm.">
				>
				["at0016"] = <
					text = <"Grote volwassene">
					description = <"Een manchet voor volwassenen met langere armen, manchet grootte ca. 16cm x 38cm.">
				>
				["at0017"] = <
					text = <"Volwassene">
					description = <"De standaard manchet voor een volwassene - manchet grootte ca. 13cm x 30cm">
				>
				["at0025"] = <
					text = <"Rechterarm">
					description = <"De rechterarm van de persoon.">
				>
				["at0026"] = <
					text = <"Linkerarm">
					description = <"De linkerarm van de persoon.">
				>
				["at0027"] = <
					text = <"Rechterdijbeen">
					description = <"Het rechterdijbeen van de persoon.">
				>
				["at0028"] = <
					text = <"Linkerdijbeen">
					description = <"De linkerdijbeen van de persoon.">
				>
				["at0033"] = <
					text = <"Opmerking">
					description = <"Opmerking over de gemeten bloeddruk">
				>
				["at1000"] = <
					text = <"Staand">
					description = <"Bloeddrukmeting bij staand individu">
				>
				["at1001"] = <
					text = <"Zittend">
					description = <"Bloeddrukmeting bij zittend (b.v. op bed of in stoel) individu">
				>
				["at1002"] = <
					text = <"Halfzittend">
					description = <"Halfzittend op het moment van de bloeddrukmeting">
				>
				["at1003"] = <
					text = <"Liggend">
					description = <"Platliggend op het moment van de bloeddrukmeting">
				>
				["at1005"] = <
					text = <"Schuinte">
					description = <"De craniocaudale schuinte van het oppervlak waarop het individu ligt op het moment van de meting">
				>
				["at1006"] = <
					text = <"Gemiddelde arteriële druk">
					description = <"De gemiddelde bloeddruk gedurende 1 cyclus van samentrekken en ontspannen van het hart.">
				>
				["at1007"] = <
					text = <"Polsdruk">
					description = <"Het verschil tussen de systolische en diastolische bloeddruk">
				>
				["at1008"] = <
					text = <"Kleine volwassene">
					description = <"Een manchet voor een kleine volwassene - manchet maat ca. 10cm x 24cm.">
				>
				["at1009"] = <
					text = <"Pediatrie/kinder">
					description = <"Een manchet voor een kind of volwassene met een dunne arm - manchet grootte ca. 8cm x 21cm.">
				>
				["at1010"] = <
					text = <"Diastolisch eindpunt">
					description = <"Om te registreren welk Korotkoff geluid gebruikt is om de diastolische druk te meten door de auscultatieve methode.">
				>
				["at1011"] = <
					text = <"Fase IV">
					description = <"Het vierde Korotkoff geluid wordt gedefinieerd als een abrupte vermindering van geluid">
				>
				["at1012"] = <
					text = <"Fase 5">
					description = <"Het vijfde Korotkoff geluid is geïdentificeerd door afwezigheid van geluiden als de manchetdruk onder diastolische bloeddruk komt.">
				>
				["at1014"] = <
					text = <"Liggend met kanteling naar linkerzijde">
					description = <"Platliggend met enige laterale kanteling, meestal gekanteld naar de linkerzijde. Gebruikelijk benodigd in het laatste trimester van de zwangerschap om aortacavale compressie te verlichten.">
				>
				["at1018"] = <
					text = <"Zuigeling">
					description = <"Een manchet voor zuigelingen - manchet maat ca. 5cm x 15cm.">
				>
				["at1019"] = <
					text = <"Neonaat">
					description = <"Een manchet voor een neonaat, er van uitgaande dat de manchet de juiste maat is voor volgroeidheid en geboortegewicht van de neonaat">
				>
				["at1020"] = <
					text = <"Rechterpols">
					description = <"De rechterpols van de persoon">
				>
				["at1021"] = <
					text = <"Linkerpols">
					description = <"De linkerpols van de persoon.">
				>
				["at1025"] = <
					text = <"Apparaat">
					description = <"Details over sphygmomanometerof ander apparaat om de bloeddruk te meten.">
				>
				["at1026"] = <
					text = <"Rechterenkel">
					description = <"De rechterenkel van de persoon">
				>
				["at1030"] = <
					text = <"Inspanning">
					description = <"Details over de lichamelijke inspanning die ondernomen wordt op het moment van de bloeddrukmeting">
				>
				["at1031"] = <
					text = <"Linkerenkel">
					description = <"De linkerenkel van de persoon">
				>
				["at1032"] = <
					text = <"Vinger">
					description = <"Een vinger van de persoon. Identificatie van de vinger kan zo nodig worden opgeslagen  in 'specifieke locatie' data element.">
				>
				["at1033"] = <
					text = <"Locatie">
					description = <"Lichaamslocatie waar de bloeddrukmeting is gemeten. Gebruik 'locatie van meting' om gebruikelijke plaatsen te selecteren. Gebruik 'specifieke locatie' om meer specifieke details of locatie te registreren, die niet in de gebruikelijke set staan of om aan een externe terminologie te refereren.">
				>
				["at1034"] = <
					text = <"Specifieke locatie">
					description = <"Specifieke details over de lichaamsplaats waar de bloeddruk is gemeten.">
				>
				["at1035"] = <
					text = <"Methodiek">
					description = <"De methode van de meting van de bloeddruk">
				>
				["at1036"] = <
					text = <"Auscultatie">
					description = <"Uitwendige meting van de bloeddruk, met gebruikmaking van een stethoscoop en Korotkoff geluiden.">
				>
				["at1037"] = <
					text = <"Palpatie">
					description = <"Uitwendige meting van de bloeddruk, met gebruikmaking van palpatie (meestal de arterie brachialis of radialis)">
				>
				["at1038"] = <
					text = <"Gemiddelde arteriële druk formule">
					description = <"Formule om de MAP (mean arterial pressure=gemiddelde arteriële druk) te berekenen (als deze data opgeslagen wordt).">
				>
				["at1039"] = <
					text = <"Machinaal">
					description = <"Uitwendige meting van de bloeddruk, met gebruikmaking van een mechanische bloeddrukmeter">
				>
				["at1040"] = <
					text = <"Invasief">
					description = <"Inwendige meting van de bloeddruk, inclusief penetratie van de huid en meting in het bloedvat.">
				>
				["at1042"] = <
					text = <"24 uur gemiddelde">
					description = <"Inschatting van de gemiddelde bloeddruk over een periode van 24 uur">
				>
				["at1043"] = <
					text = <"Slaap/waak toestand">
					description = <"Slaap/waak toestand, ondersteunt de interpretatie van de 24-uurs bloeddrukmeting.">
				>
				["at1044"] = <
					text = <"Alert en wakker">
					description = <"Individu is volledig bij bewustzijn">
				>
				["at1045"] = <
					text = <"Slapend">
					description = <"Individu is in de natuurlijke slaap.">
				>
				["at1051"] = <
					text = <"Teen">
					description = <"Een teen van de persoon. Identificatie van de vinger kan zo nodig worden opgeslagen  in 'specifieke locatie' data element.">
				>
				["at1052"] = <
					text = <"Beïnvloedende factoren">
					description = <"Opmerking over en vastleggen van andere incidentele factoren die de bloeddrukmeting zouden kunnen beïnvloeden. Bijvoorbeeld, mate van angst, of 'witte jas syndroom'; pijn of koorts; veranderingen in atmosferische druk etc.">
				>
				["at1053"] = <
					text = <"Intra-arterieel">
					description = <"Invasieve meting via lijn met transducer in een arterie. Locatie van de transducer kan, zo nodig, opgeslagen worden in 'specifieke locatie' data element.">
				>
			>
		>
		["ru"] = <
			items = <
				["at0000"] = <
					text = <"АД">
					description = <"Локальное измерение артериального давления, которое является суррогатом артериального давления в системном кровотоке. Как правило, термин относится к давления плечевой артерии на предплечье.
">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*history Structural node(en)">
				>
				["at0003"] = <
					text = <"*blood pressure(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Систолическое">
					description = <"Пик системного артериального давления - измеряется в систолиу или в фазу сокращения сердца">
				>
				["at0005"] = <
					text = <"Диастолическое">
					description = <"Минимальное системное артериальное давление - измеряется в диастолу или в фазу релаксации сердца.">
				>
				["at0006"] = <
					text = <"Любое событие">
					description = <"*Default event(en)">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"Поза">
					description = <"Поза пациента во время измерения давления.">
				>
				["at0011"] = <
					text = <"*list structure(en)">
					description = <"*list structure(en)">
				>
				["at0013"] = <
					text = <"Размер манжеты(ru)">
					description = <"Размер манжеты для измерения кровяного давления.">
				>
				["at0014"] = <
					text = <"Место измерения">
					description = <"Обобщенное место тела, в которм производится измерение артериального давления.">
				>
				["at0015"] = <
					text = <"Взрослая для бедра">
					description = <"Манжеты для бедра  взрослого- пузырь приблизительно 20см х 42см.">
				>
				["at0016"] = <
					text = <"Взрослая большая">
					description = <"Манжета для руки взрослого, увеличенного объёма -  пузырь приблизительно 16cm x 38cm.">
				>
				["at0017"] = <
					text = <"Взрослая">
					description = <"Манжета стандартная для взрослого - пузырь приблизительно 13 х 30cm.">
				>
				["at0025"] = <
					text = <"Правая рука">
					description = <"Правая рука пациента.">
				>
				["at0026"] = <
					text = <"Левая рука">
					description = <"Левая рука пациента.">
				>
				["at0027"] = <
					text = <"Правое бедро">
					description = <"Правое бедро пациента.">
				>
				["at0028"] = <
					text = <"Левое бедро">
					description = <"Левое бедро пациента.">
				>
				["at0033"] = <
					text = <"Комментарии">
					description = <"Комментарии к измерению кровяного давления.">
				>
				["at1000"] = <
					text = <"Стоя">
					description = <"Пациент стоит во время измерения АД.">
				>
				["at1001"] = <
					text = <"Сидя">
					description = <"Пациент сидит во время измерения АД (на стуле, кровати или кресле).">
				>
				["at1002"] = <
					text = <"Реклинация">
					description = <"Пациент лежит в вынужденной неизменной позе (на реклинации)во время измерения АД.">
				>
				["at1003"] = <
					text = <"Лёжа">
					description = <"Пациент лежит во время измерения АД.">
				>
				["at1005"] = <
					text = <"Наклонная поверхность">
					description = <"краниокаудальный наклон поверхности, на которой лежит пациент во время измерения АД.">
				>
				["at1006"] = <
					text = <"Среднего артериального давления крови">
					description = <"Среднее артериальное давление на всём протяжении цикла сокращения и релаксации сердца.">
				>
				["at1007"] = <
					text = <"Пульсовое давление">
					description = <"Разница между систолическим и диастолическим давлением.">
				>
				["at1008"] = <
					text = <"Взрослая малая">
					description = <"Манжета взрослая малая - пузырь приблизительно 10 x 24cm.">
				>
				["at1009"] = <
					text = <"Педиатрическая(детская)">
					description = <"Манжета для детей или взрослых с тонкой рукой - пузырь примерно 8см x 21cm.">
				>
				["at1010"] = <
					text = <"Диастолическая конечная точка">
					description = <"Запись звука Короткова который используют для определения диастолического давления с помощью метода аускультации.">
				>
				["at1011"] = <
					text = <"Фаза 4">
					description = <"Четвёртый звук Короткова, определяющийся как резкое приглушение звуков.">
				>
				["at1012"] = <
					text = <"Фаза 5">
					description = <"Пятый звук Короткова определяется отсутствием звуков, так как давление в манжете падает ниже диастолического артериального давления.">
				>
				["at1014"] = <
					text = <"Лёжа с наклоном влево">
					description = <"Лёжа на плоской поверхности с боковым наклоном, как правило, под углом по направлению с левой стороны. Обычно требуется в последнем триместре беременности, чтобы облегчить сдавление нижней полой вены.">
				>
				["at1018"] = <
					text = <"Для младенцев">
					description = <"Манжета для младенцев - пузырь приблизительно 5см x 15cm.">
				>
				["at1019"] = <
					text = <"Для новорожденных">
					description = <"Манжета для новорожденных, используется в соответствии с весом новорожденного.">
				>
				["at1020"] = <
					text = <"Правое запястье">
					description = <"Правое запястье пациента.">
				>
				["at1021"] = <
					text = <"Левое запястье">
					description = <"Левое запястье пациента.">
				>
				["at1025"] = <
					text = <"Устройство">
					description = <"Информация о сфигмоманометре или другом устройстве, используемом для измерения АД.">
				>
				["at1026"] = <
					text = <"Правая лодыжка">
					description = <"Правая лодыжка пациента.">
				>
				["at1030"] = <
					text = <"Нагрузка">
					description = <"Подробная информация о физической деятельности, осуществляемой во время измерения АД.">
				>
				["at1031"] = <
					text = <"Левая лодыжка">
					description = <"Левая лодыжка пациента">
				>
				["at1032"] = <
					text = <"Палец руки">
					description = <"Палец руки пациента. Уточнение может быть записано в элемент данных \"Точное месторасположение\", в случае необходимости.">
				>
				["at1033"] = <
					text = <"*Location(en)">
					description = <"Место тела, где измеряется АД. Используйте \"Место измерения\", чтобы выбрать из обобщённых мест. Используйте \"Точное местограсположение\", чтобы записать более конкретную информацию или место, которое не входит в обобщённый список или обратиться к внешней терминологии.">
				>
				["at1034"] = <
					text = <"Точное месторасположение">
					description = <"Конкретные сведения о месте тела, где  регистрируется АД.">
				>
				["at1035"] = <
					text = <"Метод">
					description = <"Метод измерения кровяного давления.">
				>
				["at1036"] = <
					text = <"Аускультация">
					description = <"Неинвазивный метод измерения АД с использованием стетоскопа и звуков Короткова.">
				>
				["at1037"] = <
					text = <"Пальпация">
					description = <"Неинвазивный метод измерения АД с использованием пальпации (обычно плечевой или лучевой артерии).">
				>
				["at1038"] = <
					text = <"Формула среднего артериального давления">
					description = <"Формула, используемая для вычисления СрАД (если требуется записывать).">
				>
				["at1039"] = <
					text = <"Автоматический тонометр">
					description = <"Неинвазивный метод измерения АД с помощью автоматического тонометра.">
				>
				["at1040"] = <
					text = <"Инвазивный">
					description = <"Инвазивный метод измерения АД, с помещением датчика внутри кровеносного сосуда.">
				>
				["at1042"] = <
					text = <"Среднее за 24 часа">
					description = <"Оценка среднего АД за период в 24 часа.">
				>
				["at1043"] = <
					text = <"Стадия сна(ru)">
					description = <"Стадия сна - для интерпретации записи амбулаторного измерения АД в течение 42 часов.">
				>
				["at1044"] = <
					text = <"Пробуждение и подъём">
					description = <"Пациент полностью в сознании.">
				>
				["at1045"] = <
					text = <"Сон">
					description = <"Пациент находится в состоянии естественного покоя, тело расслаблено.">
				>
				["at1051"] = <
					text = <"Палец ноги">
					description = <"Палец ноги пациента. Уточнение может быть записано в элемент данных \"Точное месторасположение\", в случае необходимости.">
				>
				["at1052"] = <
					text = <"Стохастические факторы(ru)">
					description = <"Комментарий и записи других случайных факторов, которые могут способствовать измерению артериального давления. Например,\"боязнь белого халата\" или боль и жар, изменения атмосферного давления т.д.">
				>
				["at1053"] = <
					text = <"Внутриартериальное">
					description = <"Инвазивное измерение с помощью датчика линии доступа в артерию. Расположение датчика могут быть записаны в элемент данных \"Точное месторасположение\", в случае необходимости.">
				>
			>
		>
		["fa"] = <
			items = <
				["at0000"] = <
					text = <"فشار خون">
					description = <"اندازه گیری موضعی فشار خون وریدی، که جایگزینی برای فشار وریدی در گردش خون کلی است.
معمولا واژه \"فشار خون\" به اندازه گیری فشار ورید بازویی در روی بازو گفته می شود">
				>
				["at0001"] = <
					text = <"تاریخچه">
					description = <"گره ساختاری تاریخچه ">
				>
				["at0003"] = <
					text = <"*blood pressure(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"سیستولیک">
					description = <"اوج فشار خون وریدی کلی که در سیستولیک یا فاز انقباضی چرخه گردش خون اندازه گیری می شود ">
				>
				["at0005"] = <
					text = <"دیاستولیک">
					description = <"حداقل فشار خون وریدی کلی که در دیاستولیک یا فاز انبساطی چرخه گردش خون اندازه گیری می شود">
				>
				["at0006"] = <
					text = <"هر رویداد">
					description = <"رویداد پیش فرض">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"موقعیت">
					description = <"موقعیت فرد در زمان اندازه گیری ">
				>
				["at0011"] = <
					text = <"ساختار لیست">
					description = <"ساختار لیست ">
				>
				["at0013"] = <
					text = <"اندازه کاف">
					description = <"اندازه کاف استفاده شده برای اندازه گیری فشار خون">
				>
				["at0014"] = <
					text = <"*Location of measurement(en)">
					description = <"*Common body sites where blood pressure is recorded.(en)">
				>
				["at0015"] = <
					text = <"ران بزرگسال">
					description = <"کاف استفاده شده در ران بزرگسال -اندازه مثانه 20 سانتی متر در 42 سانتی متر">
				>
				["at0016"] = <
					text = <"بزرگسال درشت">
					description = <"کاف بزرگسالان با برآمدگی بازوی بزرگتر در حدود 16 در 38 سانتیمتر">
				>
				["at0017"] = <
					text = <"*Adult(en)">
					description = <"*A cuff that is standard for an adult - bladder approx 13cm x 30cm.(en)">
				>
				["at0025"] = <
					text = <"*Right arm(en)">
					description = <"*The right arm of the person.(en)">
				>
				["at0026"] = <
					text = <"*Left arm(en)">
					description = <"*The left arm of the person.(en)">
				>
				["at0027"] = <
					text = <"*Right thigh(en)">
					description = <"*The right thigh of the person.(en)">
				>
				["at0028"] = <
					text = <"*Left thigh(en)">
					description = <"*The left thigh of the person.(en)">
				>
				["at0033"] = <
					text = <"نظر">
					description = <"نظر در مورد اندازه گیری فشار خون">
				>
				["at1000"] = <
					text = <"ایستاده">
					description = <"ایستاده در زمان اندازه گیری فشار خون">
				>
				["at1001"] = <
					text = <"نشسته">
					description = <"نشسته ( به عنوان مثال روی تخت یا صندلی) در زمان اندازه گیری فشار خون">
				>
				["at1002"] = <
					text = <"خمیده">
					description = <"خمیده در زمان اندازه گیری فشار خون">
				>
				["at1003"] = <
					text = <"خوابیده">
					description = <"خوابیده در زمان اندازه گیری فشار خون">
				>
				["at1005"] = <
					text = <"شیب">
					description = <"شیب طولی سطحی که فرد در حین اندازه گیری رون آن دراز کشیده است">
				>
				["at1006"] = <
					text = <"میانگین فشار وریدی">
					description = <"متوسط فشار خون وریدی که در کل دوره انقباظ و انبساط قلبی رخ می دهد">
				>
				["at1007"] = <
					text = <"فشار نبضی">
					description = <"تفاوت بین فشار سیستولیک و دیاستولیک">
				>
				["at1008"] = <
					text = <"*Small Adult(en)">
					description = <"*A cuff used for a small adult - bladder approx 10cm x 24cm.(en)">
				>
				["at1009"] = <
					text = <"*Paediatric/Child(en)">
					description = <"*A cuff that is appropriate for a child or adult with a thin arm - bladder approx 8cm x 21cm.(en)">
				>
				["at1010"] = <
					text = <"*Diastolic endpoint(en)">
					description = <"*Record which Korotkoff sound is used for determining diastolic pressure using auscultative method.(en)">
				>
				["at1011"] = <
					text = <"*Phase IV(en)">
					description = <"*The fourth Korotkoff sound is identified as an abrupt muffling of sounds.(en)">
				>
				["at1012"] = <
					text = <"*Phase V(en)">
					description = <"*The fifth Korotkoff sound is identified by absence of sounds as the cuff pressure drops below the diastolic blood pressure.(en)">
				>
				["at1014"] = <
					text = <"خوابیده  به چپ">
					description = <"خوابیدن صاف با کمی تمایل به یک سمت، معمولا به جهت چپ میل کرده و عموما در سه ماهه آخر حاملگی برای تسکین فشار آئورت نیاز به آن است">
				>
				["at1018"] = <
					text = <"*Infant(en)">
					description = <"*A cuff used for infants - bladder approx 5cm x 15cm.(en)">
				>
				["at1019"] = <
					text = <"*Neonatal(en)">
					description = <"*A cuff used for a neonate, assuming cuff is the appropriate size for maturity and birthweight of the neonate.(en)">
				>
				["at1020"] = <
					text = <"*Right wrist(en)">
					description = <"*The right wrist of the subject.(en)">
				>
				["at1021"] = <
					text = <"*Left wrist(en)">
					description = <"*The left wrist of the subject.(en)">
				>
				["at1025"] = <
					text = <"*Device(en)">
					description = <"*Details about sphygmomanometer or other device used to measure the blood pressure.(en)">
				>
				["at1026"] = <
					text = <"*Right ankle(en)">
					description = <"*The right ankle of the subject.(en)">
				>
				["at1030"] = <
					text = <"تقلا">
					description = <"جزییاتی درباره فعالیت فیزیکی انجام شده در زمان اندازه گیری فشار خون ">
				>
				["at1031"] = <
					text = <"*Left ankle(en)">
					description = <"*The left ankle of the subject.(en)">
				>
				["at1032"] = <
					text = <"*Finger(en)">
					description = <"*A finger of the subject.  Identification of the finger can be recorded in 'Specific Location' data element, if required.(en)">
				>
				["at1033"] = <
					text = <"*Location(en)">
					description = <"*Body location where blood pressure is measured.  Use 'Location of measurement' to select from common sites.  Use 'Specific location' to record more specific details or a site that is not in the common set or to refer to an external terminology.(en)">
				>
				["at1034"] = <
					text = <"*Specific location(en)">
					description = <"*Specific details about the body site where blood pressure is recorded.(en)">
				>
				["at1035"] = <
					text = <"*Method(en)">
					description = <"*Method of measurement of blood pressure.(en)">
				>
				["at1036"] = <
					text = <"*Auscultation(en)">
					description = <"*Method of measuring blood pressure externally, using a stethoscope and Korotkoff sounds.(en)">
				>
				["at1037"] = <
					text = <"*Palpation(en)">
					description = <"*Method of measuring blood pressure externally, using palpation (usually of the brachial or radial arteries).(en)">
				>
				["at1038"] = <
					text = <"*Mean Arterial Pressure Formula(en)">
					description = <"*Formula used to calculate the MAP (if recorded in data).(en)">
				>
				["at1039"] = <
					text = <"*Machine(en)">
					description = <"*Method of measuring blood pressure externally, using a blood pressure machine.(en)">
				>
				["at1040"] = <
					text = <"*Invasive(en)">
					description = <"*Method of measuring blood pressure internally ie involving penetration of the skin and measuring inside blood vessels.(en)">
				>
				["at1042"] = <
					text = <"میانگین 24 ساعته">
					description = <"برآورد میانگین فشار خون در دوره زمانی 24 ساعته">
				>
				["at1043"] = <
					text = <"وضعیت خواب">
					description = <"وضعیت خواب- به تفسیر ثبتهای صورت گرفته از فشار خون در خانه در طول 24 ساعت کمک می کند ">
				>
				["at1044"] = <
					text = <"هشیار و بیدار">
					description = <"فرد کاملا به هوش است ">
				>
				["at1045"] = <
					text = <"خوابیده">
					description = <"فرد در حالت طبیعی استراحت بدنی است">
				>
				["at1051"] = <
					text = <"*Toe(en)">
					description = <"*A toe of the subject.   Identification of the toe can be recorded in 'Specific Location' data element, if required.(en)">
				>
				["at1052"] = <
					text = <"عوامل مبهم">
					description = <"نظردهی و ثبت سایر عوامل ضمنی که ممکن است به اندازه گیری فشار خون کمک کنند . به عنوان مثال سطح اضطراب یا \"سندرم روپوش سفید\"، درد یا تب ، تغییرات فشار جوی و غیره ">
				>
				["at1053"] = <
					text = <"*Intra-arterial(en)">
					description = <"*Invasive measurement via transducer access line within an artery. Location of the transducer can be recorded in 'Specific Location' data element, if required.(en)">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"ضغط الدم">
					description = <"قياس موضعي لضغط الدم الشرياني و الذي يحل محل الضغط الشرياني في الدورة الدموية الجهازية. 
و عادة ما يستخدم مصطلح \"ضغط الدم\" لللإشارة إلى قياس ضغط دم الشريان العضُدي في أعلى الذراع.">
				>
				["at0001"] = <
					text = <"التاريخ">
					description = <"العقدة التركيبية للتاريخ">
				>
				["at0003"] = <
					text = <"*blood pressure(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"الانقباضي">
					description = <"ذروة ضغط الدم الشرياني الجهازي - يتم قياسه في طور الانقباض من دورة القلب">
				>
				["at0005"] = <
					text = <"الانبساطي">
					description = <"الحد الأدني لضغط الدم الشرياني الجهازي - يتم قياسها في طور الانبساط - الارتخاء من دورة القلب">
				>
				["at0006"] = <
					text = <"إحدى الوقائع">
					description = <"الواقعة التلقائية">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"الموضع">
					description = <"موضع الشخص في وقت القياس">
				>
				["at0011"] = <
					text = <"تركيب القائمة">
					description = <"تركيب القائمة">
				>
				["at0013"] = <
					text = <"حجم الكُفَّة">
					description = <"حجم الكُفَّة المستخدمة في قياس ضغط الدم">
					comment = <"Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Human blood pressure determination by sphygmomanometry. Circulation 1993;88;2460-2470. ">
				>
				["at0014"] = <
					text = <"موضع القياس">
					description = <"الأماكن المعتادة من الجسم التي يتم فيها عادة قياس ضغط الدم">
				>
				["at0015"] = <
					text = <"فخذ البالغ">
					description = <"كفة تستخدم لفخذ البالغ - مثانة/ كيسة من 20 سينتيمتر * 42 سينتيمتر تقريبا">
				>
				["at0016"] = <
					text = <"بالغ كبير">
					description = <"كفة للبالغين ذوي الأذرع الكبيرة - المثانة/ الكيسة 16 سينتيمتر * 38 سينتيمتر تقريبا">
				>
				["at0017"] = <
					text = <"البالغ">
					description = <"كفة عيارية للبالغين - مثانة من 13 سينتيمتر * 30 سينتيمتر تقريبا">
				>
				["at0025"] = <
					text = <"الذراع الأيمن">
					description = <"الذراع الأيمن للشخص">
				>
				["at0026"] = <
					text = <"الذراع الأيسر">
					description = <"الذراع الأيسر للشخص">
				>
				["at0027"] = <
					text = <"الفخذ الأيمن">
					description = <"الفخذ الأيمن للشخص">
				>
				["at0028"] = <
					text = <"الفخذ الأيسر">
					description = <"الفخذ الأيسر للشخص">
				>
				["at0033"] = <
					text = <"تعليق">
					description = <"تعليق حول قياس ضغط الدم">
				>
				["at1000"] = <
					text = <"واقف">
					description = <"الشخص واقف عند القيام بقياس ضغط الدم">
				>
				["at1001"] = <
					text = <"جالس">
					description = <"الشخص جالس (مثلا على سرير أو كرسي) عند القيام بقياس ضغط الدم">
				>
				["at1002"] = <
					text = <"مضطجع">
					description = <"الشخص مضطجع عند القيام بقياس ضغط الدم">
				>
				["at1003"] = <
					text = <"مستلقٍ">
					description = <"الشخص مستلقٍ بشكل مستوٍ عند القيام بقياس ضغط الدم">
				>
				["at1005"] = <
					text = <"الانحناء">
					description = <"الانحناء الرأسي الذنبي على السطح الذي يستلقي عليه الشخص في أثناء القياس">
				>
				["at1006"] = <
					text = <"متوسط الضغط الشرياني">
					description = <"متوسط الضغط الشرياني الذي يحدث خلال جميع أطوار دورة القلب الواحدة من انقباض و انبساط/ ارتخاء">
				>
				["at1007"] = <
					text = <"الضغط عند النبض">
					description = <"الفرق بين ضغط الدم الانقباضي و الانبساطي">
				>
				["at1008"] = <
					text = <"البالغ الصغير">
					description = <"كفة تستخدم للبالغ الصغير - مثانة/ كيسة من 10 سينتيمتر * 24 سينتيمتر تقريبا">
				>
				["at1009"] = <
					text = <"طفل">
					description = <"كفة تستخدم للطفل أو البالغ ذي الذراع الرفيعة - من 8 سينتيمتر * 21 سينتيمتر تقريبا">
				>
				["at1010"] = <
					text = <"النقطة النهائية الانبساطية/ الارتخائية">
					description = <"تستخدم أصوات كورتكوف لتحديد ضغط الدم الانبساطي باستخدام طريقة التسمُّع">
				>
				["at1011"] = <
					text = <"الطور الرابع">
					description = <"يتم التعرف على صوت كورتكوف الرابع على أنه تخفيت منفصل">
				>
				["at1012"] = <
					text = <"الطور الخامس">
					description = <"يتم التعرف على صوت كورتكوف الخامس بغياب الأصوات حيث ينخفض ضغط الكفة تحت ضغط الدم الانبساطي">
				>
				["at1014"] = <
					text = <"مستلق و مائل لجانبه الأيسر">
					description = <"الشخص مستلق بشكل مستو مع ميل جانبي بزاوية تجاه جانبه الأيسر. عادة ما يُحتاج إلى هذا الوضع في الأثلوث الأخير من الحمل لتخفيف الانضغاط الأبهري الجوفي">
				>
				["at1018"] = <
					text = <"رضيع">
					description = <"كفة تستخدم للرضيع - مثانة/ كيسة من 5 سينتيمتر * 15 سينتيمتر تقريبا">
				>
				["at1019"] = <
					text = <"حديث الولادة">
					description = <"الكفة المستخدمة لحديثي الولادة, على افتراض أن الكفة مناسبة للحجم و النضج و الوزن عند ولادة الطفل">
				>
				["at1020"] = <
					text = <"الساعد الأيمن">
					description = <"الساعد الأيمن للشخص">
				>
				["at1021"] = <
					text = <"الساعد الأيسر">
					description = <"الساعد الأيسر للشخص">
				>
				["at1025"] = <
					text = <"الجهيزة">
					description = <"تفاصيل حول جهاز ضغط الدم الزئبقي أو جهيزة أخرى تستخدم لقياس ضغط الدم">
				>
				["at1026"] = <
					text = <"الكاحل الأيمن">
					description = <"الكاحل الأيمن للشخص">
				>
				["at1030"] = <
					text = <"المجهود">
					description = <"تفاصيل حول النشاط البدني الذي يتم القيام به في وقت قياس ضغط الدم.">
				>
				["at1031"] = <
					text = <"الكاحل الأيسر">
					description = <"الكاحل الأيسر للشخص">
				>
				["at1032"] = <
					text = <"الأصبع">
					description = <"أصبع الشخص. تعريف الأصبع الذي يتم تسجيله كنوع بيانات (مكان معيَّن), حسب الحاجة">
				>
				["at1033"] = <
					text = <"الموضع">
					description = <"الموضع من الجسم الذي يتم قياس ضغط الدم عنده. 
استخدم (موضع القياس) للاختيار من الأماكن المعتادة. 
استخدم (موضع معيَّن) لتسجيل تفاصيل أكثر تحديدا أو موضعا ليس في مجموعة الخيارات المعتادة أو للإشارة إلى مجموعة مصطلحات خارجية.">
				>
				["at1034"] = <
					text = <"موقع معين">
					description = <"تفاصلي معينة عن الموقع من الجسم الذي يتم فيه قياس ضغط الدم">
				>
				["at1035"] = <
					text = <"الطريقة">
					description = <"طريقة قياس ضغط الدم">
				>
				["at1036"] = <
					text = <"التسمع">
					description = <"طريقة خارجية لقياس ضغط الدم, باستخدام سماعة طبيب أو أصوات كوروتكوف">
				>
				["at1037"] = <
					text = <"الجس">
					description = <"طريقة خارجية لقياس ضغط الدم, باستخدام الجس - عادةً الشرايين الذراعية و الكعبري">
				>
				["at1038"] = <
					text = <"صيغة متوسط الضغط الشرياني">
					description = <"الصيغة المستخدمة لقياس متوسط الضغط الشرياني - إذا تم تسجيل بياناتها">
				>
				["at1039"] = <
					text = <"الآلة">
					description = <"طريقة خارجية لقياس ضغط الدم بالستخدام آلة قياس ضغط الدم">
				>
				["at1040"] = <
					text = <"باضع">
					description = <"طريقة داخلية لقيسا ضغط الدم, و ذلك يعني اختراق الجلد/ البشرة داخل الأوعية الدموية">
				>
				["at1042"] = <
					text = <"المتوسط خلال 24 ساعة">
					description = <"تقدير متوسط ضغط الدم خلال فترة من 24 ساعة">
				>
				["at1043"] = <
					text = <"حالة النوم">
					description = <"حالة النوم - تدعم تفسير قياسات ضغط الدم المِسيارية خلال 24 ساعة">
				>
				["at1044"] = <
					text = <"متنبه و يقظ">
					description = <"الشخص واعٍ بشكل كامل">
				>
				["at1045"] = <
					text = <"نائم">
					description = <"الشخص في الحالة الطبيعية الخاصة بالراحة الجسدية">
				>
				["at1051"] = <
					text = <"أصبع القدم">
					description = <"أصبع قدم الشخص. 
يمكن تسجيل تعريف أصبع القدم كنوع بيانات (موضع معيَّن), حسب الحاجة.">
				>
				["at1052"] = <
					text = <"العوامل المربكة">
					description = <"تعليق حول و تسجيل للعوامل الطارئة التي قد تسهم في قياس ضغط الدم. مثلا, مستوى القلق أو متلازمة البالطو الأبيض أو الألم أو الحمى أو التغييرات في الضغط الجوي,, إلى آخره">
				>
				["at1053"] = <
					text = <"داخل الشريان">
					description = <"قياس باضع عن طريق دخول خط تِرجام في داخل الشريان. 
يمكن تسجيل الترجام كنوع بيانات (موضع معيَّن), حسب الحاجة.">
				>
			>
		>
		["es-ar"] = <
			items = <
				["at0000"] = <
					text = <"Presión Arterial">
					description = <"La medición local de la tensión arterial que deriva de la medida de la presión arterial en la circulación sistémica. Comúnmente el uso de 'presión arterial' se refiere a la medida de la presión de la arteria braquial por encima del pliegue del codo.">
				>
				["at0001"] = <
					text = <"historia">
					description = <"historia Nodo estructural">
				>
				["at0003"] = <
					text = <"*blood pressure(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Sistólica">
					description = <"Presión arterial sistólica pico - medido en sístole o la fase de contracción del ciclo cardíaco">
				>
				["at0005"] = <
					text = <"Diástole">
					description = <"Presión arterial sistémica mínima - medido durante la diástole o fase de relajación del ciclo cardíaco.">
				>
				["at0006"] = <
					text = <"cualquier evento">
					description = <"Evento por defecto">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"Posición">
					description = <"La posición del individuo en el momento del registro.">
				>
				["at0011"] = <
					text = <"estructura de lista">
					description = <"estructura tipo lista">
				>
				["at0013"] = <
					text = <"Tamaño del manguito">
					description = <"El tamaño del manguito usado para la toma de la presión arterial">
					comment = <"Perloff D, Grim C, Flack J, Frohlich ED, Hill M, McDonald M, Morgenstern BZ. Presión arterial humana determinado por esfingomanómetro. Circulation 1993;88;2460-2470.">
				>
				["at0014"] = <
					text = <"Localización de la medida">
					description = <"Sitios comunes del cuerpo donde se registra la presión arterial">
				>
				["at0015"] = <
					text = <"Muslo Adulto">
					description = <"Un manguito usado para el muslo del adulto - cámara de caucho aproximadamente de 20cm x 42 cm">
				>
				["at0016"] = <
					text = <"Adulto grande">
					description = <"Un manguito para adultos con brazos mas grandes - cámara de caucho aproximadamente de 16cm x 38cm.">
				>
				["at0017"] = <
					text = <"Adulto">
					description = <"Un manguito estándar para adulto - cámara de caucho approximadamente de 13cm x 30cm.">
				>
				["at0025"] = <
					text = <"Brazo derecho">
					description = <"El brazo derecho del individuo">
				>
				["at0026"] = <
					text = <"Brazo izquierdo">
					description = <"El brazo izquierdo del individuo">
				>
				["at0027"] = <
					text = <"Muslo derecho">
					description = <"El muslo derecho del individuo">
				>
				["at0028"] = <
					text = <"Muslo izquierdo">
					description = <"El muslo izquierdo del individuo">
				>
				["at0033"] = <
					text = <"Comentario">
					description = <"Comentario sobre la medición de la presión sanguínea">
				>
				["at1000"] = <
					text = <"De pie">
					description = <"De pie al momento de la medición de la tensión arterial.">
				>
				["at1001"] = <
					text = <"Sentado">
					description = <"Sentado (en la cama o en una silla) durante el registro de la presión arterial ">
				>
				["at1002"] = <
					text = <"Reclinado">
					description = <"Reclinado (semisentado) durante el registro de la presión arterial">
				>
				["at1003"] = <
					text = <"Acostado">
					description = <"Acostado horizontal durante la medición de la presión arterial">
				>
				["at1005"] = <
					text = <"Inclinación">
					description = <"La inclinación craneo-caudal de la superficie sobre la cual el sujeto esta acostado al momento de la medición">
				>
				["at1006"] = <
					text = <"Presión Arterial Media">
					description = <"La presión arterial promedio que ocurre durante el ciclo entero de la contracción y relajación del corazon">
				>
				["at1007"] = <
					text = <"Presión de Pulso">
					description = <"La diferencia entre la presión sistólica y la presión diastólica">
				>
				["at1008"] = <
					text = <"Adulto pequeño">
					description = <"Un manguito usado para adulto pequeño - cámara de caucho approximadamente de 10cm x 24cm.">
				>
				["at1009"] = <
					text = <"Pediátrico/Niño">
					description = <"Un manguito que es apropiado para un niño o un adulto con brazos delgados - cámara de caucho approximadamente 8cm x 21cm.">
				>
				["at1010"] = <
					text = <"Punto final diastólica">
					description = <"Registro usando los sonidos de Korotkoff para determinar la presión diastólica">
				>
				["at1011"] = <
					text = <"Fase IV">
					description = <"El cuarto sonido de Korotkoff se identifica como una abrupta amortiguación de sonidos.">
				>
				["at1012"] = <
					text = <"Fase V">
					description = <"El quinto sonido de Korotkoff se identifica como la ausencia de sonidos a medida que la presión del manguito insuflado cae por debajo de la presión arterial diastólica.">
				>
				["at1014"] = <
					text = <"Acostado e inclinado levemente sobre su costado izquierdo">
					description = <"Acostado horizontal e inclinado levemente sobre su costado izquierdo. Comúnmente se requiere durante el último trimestre del embarazo para aliviar la compresión aortocava.">
				>
				["at1018"] = <
					text = <"Infantil">
					description = <"Un manguito usado para infantes - cámara de caucho approximadamente de 5cm x 15cm.">
				>
				["at1019"] = <
					text = <"Neonatal">
					description = <"Un manguito usado para neonatos, asumiendo que es del tamaño adecuado para la madurez y el peso corporal del neonato.">
				>
				["at1020"] = <
					text = <"Muñeca derecha">
					description = <"La muñeca derecha del individuo.">
				>
				["at1021"] = <
					text = <"Muñeca izquierda">
					description = <"La muñeca inquierda del individuo.">
				>
				["at1025"] = <
					text = <"Dispositivo">
					description = <"Detalles del esfingomanómetro u otro dispositivo usado para medir la presión arterial.">
				>
				["at1026"] = <
					text = <"Tobillo derecho ">
					description = <"El tobillo derecho del individuo.">
				>
				["at1030"] = <
					text = <"Ejercicio">
					description = <"Detalles de la actividad física realizados durante la medición de la presión arterial ">
				>
				["at1031"] = <
					text = <"Tobillo izquierdo">
					description = <"El tobillo izquierdo del individuo">
				>
				["at1032"] = <
					text = <"Dedo">
					description = <"Un dedo del individuo. La identificación del dedo puede ser registrado en el data elemento: 'Localización específica' si se requiere. ">
				>
				["at1033"] = <
					text = <"Localización">
					description = <"Localización del cuerpo donde se mide la presión arterial. Use 'Localización de la medida' para seleccionar los sitios más comunes. Use 'Localización específica' para registrar detalles mas específicos o un sitio que no pertenece al conjunto mas común o para referirse a una terminología externa.">
				>
				["at1034"] = <
					text = <"Localización específica">
					description = <"Detalles específicos sobre el sitio corporal donde se registro la presión arterial">
				>
				["at1035"] = <
					text = <"Método">
					description = <"Método de la medición de la presión arterial">
				>
				["at1036"] = <
					text = <"Auscultación">
					description = <"Método de la medición de la presión arterial externa, usando un estetoscopio y los sonidos de Korotkoff">
				>
				["at1037"] = <
					text = <"Palpación">
					description = <"Método de medición de la presión arterial externa, usando palpación (normalmente de la arteria humeral o radial).">
				>
				["at1038"] = <
					text = <"Fórmula de la Presión Arterial Media (PAM)">
					description = <"Fórmula usada para calcular la PAM (si se registra en el campo data)">
				>
				["at1039"] = <
					text = <"Máquina">
					description = <"Método de medición de la presión arterial externa, utilizando un monitor automático (mecánico) de presión arterial">
				>
				["at1040"] = <
					text = <"Invasivo">
					description = <"Método de medición de la presión arterial interna o sea invasiva: punción de la piel y la introducción de un cateter para medir dentro de un vaso sanguíneo.">
				>
				["at1042"] = <
					text = <"Promedio de 24 horas">
					description = <"Estimativo de la media de la presión arterial sobre un período de 24 horas">
				>
				["at1043"] = <
					text = <"Estado del sueño">
					description = <"Estado del sueño - soporta la interpretación de los registros de presión arterial ambulatorios de 24 horas">
				>
				["at1044"] = <
					text = <"Alerta y despierto">
					description = <"El sujeto esta plenamente consciente">
				>
				["at1045"] = <
					text = <"Dormido">
					description = <"El sujeto esta en un estado natural de sueño corporal">
				>
				["at1051"] = <
					text = <"Dedo del pie">
					description = <"Un dedo del pie del individuo.  La identificación del dedo del pie puede ser registrado en el data elemento: 'Localización específica' si se requiere. ">
				>
				["at1052"] = <
					text = <"Factores confluentes">
					description = <"Comentario y registro sobre otros factores que pueden incidir sobre la medición de la presión arterial. Por ejemplo: nivel de ansiedad o \"síndrome del guardapolvo blanco\"; dolor o fiebre; cambios en la presión atmosférica etc.">
				>
				["at1053"] = <
					text = <"Intra-arterial">
					description = <"Medición invasiva mediante una vía de acceso transductor, dentro de la arteria.  La localización del transductor puede ser registrado en el data elemento: 'Localización específica' si se requiere. ">
				>
			>
		>
		["pt-br"] = <
			items = <
				["at0000"] = <
					text = <"Pressão Arterial">
					description = <"A medida local da pressão sanguínea arterial, a qual é uma substituta da pressão arterial na circulação arterial sistêmica. Mais comumente o uso do termo pressão arterial se refere à medida da pressão da artéria braquial no antebraço.">
				>
				["at0001"] = <
					text = <"história">
					description = <"nodo Estrutural história">
				>
				["at0003"] = <
					text = <"*blood pressure(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Sistólica">
					description = <"Pressão arterial sistêmica máxima - medida na fase sistólica ou de contração do ciclo cardíaco.">
				>
				["at0005"] = <
					text = <"Diastólica">
					description = <"Pressão arterial sistêmica mínima - medida na fase diastólica ou de  dilatação do ciclo cardíaco.">
				>
				["at0006"] = <
					text = <"qualquer evento">
					description = <"evento Default, padrão predeterminado">
				>
				["at0007"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0008"] = <
					text = <"Posição">
					description = <"A posição do sujeito na hora da medida.">
				>
				["at0011"] = <
					text = <"estrutura de lista">
					description = <"estrutura de lista">
				>
				["at0013"] = <
					text = <"Tamanho da braçadeira">
					description = <"Tamanho da braçadeira  usada para medir a pressão arterial.">
					comment = <"Sem  comentários">
				>
				["at0014"] = <
					text = <"Local de Medida">
					description = <"Locais do corpo mais comuns onde a pressão arterial é medida.">
				>
				["at0015"] = <
					text = <"Coxa de adulto">
					description = <"Uma braçadeira  usada na coxa de um aduto - manguito de aproximadamente 20cm x 42cm.">
				>
				["at0016"] = <
					text = <"Adulto Grande">
					description = <"Uma braçadeira para adultos com braço largo - manguito de aproximadamente 16cm x 38cm.">
				>
				["at0017"] = <
					text = <"Adulto">
					description = <"Uma braçadeira padrão para adultos - manguito de aproximadamente 13cm x 30cm.">
				>
				["at0025"] = <
					text = <"Braço direito">
					description = <"O braço direito da pessoa.">
				>
				["at0026"] = <
					text = <"Braço esquerdo">
					description = <"O braço esquerdo da pessoa.">
				>
				["at0027"] = <
					text = <"Coxa direita">
					description = <"A coxa direita da pessoa.">
				>
				["at0028"] = <
					text = <"Coxa esquerda">
					description = <"A coxa esquerda da pessoa.">
				>
				["at0033"] = <
					text = <"Comentários">
					description = <"Comentários sobre a medida da pressão arterial.">
				>
				["at1000"] = <
					text = <"Em pé">
					description = <"Em pé na hora da medida da pressão arterial.">
				>
				["at1001"] = <
					text = <"Sentado">
					description = <"Sentado (por exemplo na cama ou em uma cadeira) na hora da medida da pressão arterial.">
				>
				["at1002"] = <
					text = <"Reclinado">
					description = <"Reclinado na hora da medida da pressão arterial.">
				>
				["at1003"] = <
					text = <"Deitado">
					description = <"Deitado sem reclinação hora da medida da pressão arterial.">
				>
				["at1005"] = <
					text = <"Nível de inclinação">
					description = <"O nível de  inclinação crânio-caudal da superfície sobre a qual a pessoa está deitada no momento da medição.">
				>
				["at1006"] = <
					text = <"Pressão arterial Média">
					description = <"A pressão arterial média que ocorrre ao longo de todo o  ciclo de contração e dilatação do coração.">
				>
				["at1007"] = <
					text = <"Pressão de Pulso">
					description = <"A diferença entre a pressão sistólica e diastólica.">
				>
				["at1008"] = <
					text = <"Adulto pequeno">
					description = <"Uma braçadeira usada para adultos pequenos -manguito de aproximadamente 10cm x 24cm.">
				>
				["at1009"] = <
					text = <"Criança/Pediátrico">
					description = <"Manguito apropriao para uma criança ou um adulto com um braço fino - bolsa de aproximadamente 8cm x 21cm.">
				>
				["at1010"] = <
					text = <"Final da diástole">
					description = <"Registro  do som Korotkoff usado para determinar a pressão arterial diastólica, usando o método auscultativo.">
				>
				["at1011"] = <
					text = <"Fhase IV.">
					description = <"O quarto som de  Korotkoff é  identificado como um súbito abafamento dos sons.">
				>
				["at1012"] = <
					text = <"Phase V">
					description = <"O quinto som de Korotkoff é identificado pela ausência de sons,  pois a pressão da braçadeira cai abaixo da pressão diastólica do sangue.">
				>
				["at1014"] = <
					text = <"Deitado com inclinação para esquerda">
					description = <"Deitado sem reclinação com alguma inclinação lateral, usualmente com angulação para o lado esquerdo. Comumente requerido no último trimestre da gravidez para aliviar a compressão aortocaval.">
				>
				["at1018"] = <
					text = <"Criança pequena ">
					description = <"Uma braçadeira utilizada em crianças  pequenas - manguito de aproximadamente 5cm x 15cm.">
				>
				["at1019"] = <
					text = <"Neonatal">
					description = <"Uma braçadeira usada para um recém-nascido, supondo que o tamanho é apropriado para a maturidade e o peso ao nascer do neonato.">
				>
				["at1020"] = <
					text = <"Pulso direito">
					description = <"O pulso direito da pessoa.">
				>
				["at1021"] = <
					text = <"Pulso esquerdo">
					description = <"O pulso esquerdo da pessoa.">
				>
				["at1025"] = <
					text = <"Aparelho">
					description = <"Detalhes sobre o esfigmomanômetro ou outro aparelho utilizado para medir a pressão sanguínea.">
				>
				["at1026"] = <
					text = <"Tornozelo direito">
					description = <"O tornozelo direito da pessoa.">
				>
				["at1030"] = <
					text = <"Esforço físico">
					description = <"Detalhes sobre atividade física realizada na hora da medida da pressão arterial.">
				>
				["at1031"] = <
					text = <"Tornozelo esquerdo">
					description = <"O tornozelo esquerdo da pessoa.">
				>
				["at1032"] = <
					text = <"Dedo da mão">
					description = <"O dedo da mão da pessoa. A identificação do dedo pode ser registrada no elemento de dado 'Local Específico', se requerido.">
				>
				["at1033"] = <
					text = <"Local">
					description = <"Local do corpo onde  foi medida a pressão arterial.  Use  'Local da Medida' para selecionar entre os locais mais comuns.  Use 'Local Específico' para registrar detalhes mais específicos ou um local que não está representado no conjunto comum ou para se referenciar a uma terminologia externa.">
				>
				["at1034"] = <
					text = <"Local Específico">
					description = <"Detalhes específicos sobre o local do corpo onde a pressão arterial é registrada.">
				>
				["at1035"] = <
					text = <"Método">
					description = <"Método de medida da pressão arterial.">
				>
				["at1036"] = <
					text = <"Ausculta">
					description = <"Método de medir a pressão externamente, usando o estetoscópiso e os sons Korotkoff.">
				>
				["at1037"] = <
					text = <"Palpação">
					description = <"Método de medir a pressão arterial externamente, usando a palpação (geralmente artérias braquiais ou radiais).">
				>
				["at1038"] = <
					text = <"Fórmula de Pressão Arterial Média">
					description = <"Fórmula usada para calcular a pressão arterial média (PAM), se registrada em dados.">
				>
				["at1039"] = <
					text = <"Aparelho de pressão">
					description = <"Método de medir a pressão arterial externamente, usando o aparelho de pressão arterial.">
				>
				["at1040"] = <
					text = <"Invasivo">
					description = <"Método de medir a pressão arterial internamente, isto é, envolvendo a penetração da pele e a medida interior dos vasos sanguíneos.">
				>
				["at1042"] = <
					text = <"Media de 24 horas">
					description = <"Estimativa da pressão arterial média em um período de 24 horas.">
				>
				["at1043"] = <
					text = <"Status do sono">
					description = <"Status do sono - apóia a interpretação do registro do mapa de pressão arterial (ambulatorial de 24 horas).">
				>
				["at1044"] = <
					text = <"Alerta e acordado">
					description = <"Sujeito está totalmente consciente.">
				>
				["at1045"] = <
					text = <"Dormindo">
					description = <"Sujeito está no estado natural de descanso corporal.">
				>
				["at1051"] = <
					text = <"Dedo do pé">
					description = <"O dedo do pé da pessoa. A identificação do dedo do pé pode ser registrada  no elemento de dado 'Local Específico', se requerido.">
				>
				["at1052"] = <
					text = <"Fatores confundidores">
					description = <"Comentários sobre e registros de outros fatores incidentais que possam estar contribuindo na medida da pressão sanguínea. Por exemplo, nível de ansiedade ou \"síndrome do jaleco branco\"; dor ou febre; mudanças na pressão atmosférica, etc.">
				>
				["at1053"] = <
					text = <"Intra-arterial">
					description = <"Medida invasiva da pressão em uma artéria acessada  por um cateter . Local do transductor pode ser registrado no elemento de dado  'Local Específico', se requerido.">
				>
			>
		>
	>
	term_bindings = <
		["SNOMED-CT"] = <
			items = <
				["at0000"] = <[SNOMED-CT(2003)::163020007]>
				["at0004"] = <[SNOMED-CT(2003)::163030003]>
				["at0005"] = <[SNOMED-CT(2003)::163031004]>
				["at0013"] = <[SNOMED-CT(2003)::246153002]>
			>
		>
	>

```
Body Surface (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.body_surface_area.v1

concept
	[at0000]	-- Body Surface Area
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Cailin Lowry">
		["organisation"] = <"The Chris O'Brien Lifehouse at RPA">
		["email"] = <"cailin.lowry@lifehouserpa.org.au">
		["date"] = <"2012-12-07">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the measured or calculated surface area of a human body.">
			use = <"Used to measure or calculate the surface area of the human body to support clinical decision-making for example determining an appropriate doses of drugs with narrow therapeutic index like many chemotherapy medications and other clinical applications such as calculating cardiac index.">
			keywords = <"body", "surface", "area", "BSA">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Christian Ghan, Lifehouse, Australia", ...>
	other_details = <
		["MD5-CAM-1.0.1"] = <"48199A0696E7E86508042F451325ACCF">
	>

definition
	OBSERVATION[at0000] matches {	-- Body Surface Area
		data matches {
			HISTORY[at0001] matches {	-- Event Series
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0002] occurrences matches {0..1} matches {	-- Any event
						data matches {
							ITEM_TREE[at0003] matches {	-- Tree
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0004] matches {	-- Body Surface Area
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::335]>
												list = <
													["1"] = <
														units = <"m2">
														precision = <|2|>
													>
												>
											>
										}
									}
								}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0005] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0006] occurrences matches {0..1} matches {	-- Formula
						value matches {
							DV_TEXT matches {*}
						}
					}
				}
			}
		}
	}


ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Body Surface Area">
					description = <"The measured or calculated surface area of a human body, commonly referred to as BSA.">
				>
				["at0001"] = <
					text = <"Event Series">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.">
				>
				["at0003"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Body Surface Area">
					description = <"The measured or calculated surface area of a human body.">
				>
				["at0005"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0006"] = <
					text = <"Formula">
					description = <"Formula used to calculate the BSA.">
				>
			>
		>
	>

```
Body Temprature (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.body_temperature.v1

concept
	[at0000]	-- Body temperature
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["nb"] = <
			language = <[ISO_639-1::nb]>
			author = <
				["name"] = <"Jostein Ven">
				["organisation"] = <"KITH">
				["email"] = <"jostein.ven@kith.no">
			>
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			author = <
				["name"] = <"Shahla Foozonkhah">
				["organisation"] = <"Ocean Informatics">
			>
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Sebastian Garde">
				["organisation"] = <"Ocean Informatics">
			>
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			author = <
				["name"] = <"Domingo Liotta">
				["organisation"] = <"University of Morón">
			>
			accreditation = <"University of Morón">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			author = <
				["name"] = <"Marco Borges">
				["organisation"] = <"P2D">
				["email"] = <"marco.borges@p2d.com.br">
			>
			accreditation = <"P2D Health Advisor Council">
		>
		["es"] = <
			language = <[ISO_639-1::es]>
			author = <
				["name"] = <"Domingo Liotta">
				["organisation"] = <"University of Morón">
			>
			accreditation = <"University of Morón">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			author = <
				["name"] = <"Igor Lizunov">
				["email"] = <"i.lizunov@infinnity.ru">
			>
		>
	>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"18/05/2004">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the measured temperature of a person - as a surrogate for the temperature of the whole body.">
			use = <"Used for recording the whole body temperature of a person or body.
Additional clusters can be included to provide additional state data - including environmental conditions, menstrual cycle details and exertion details, where appropriate.
Please Note: The site and method of recording may need to be displayed to the end user to facilitate accurate interpretation of the temperature recorded.">
			keywords = <"temperature", "body", "core", "fever", "hypothermia", "hyperthermia">
			misuse = <"This archetype is not to be used to record the temperature of any other object.
This archetype is not to be used to record the temperature of a part of the body in isolation e.g. temperature of the sole of the foot as a part of chronic diabetes management.">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"Zur Messung der Temperatur einer Person - als Surrogat for die Temperatur des gesamten Körpers.">
			use = <"Benutzt zur Aufzeichnung der gesamten Körpertemperatur einer Person oder eines Körpers.



Wenn benötigt, können zusätzliche Cluster Archetypen eingefügt werden, um zusätzliche Statusdaten bereitzustellen - darunter Details zu Umgebungsbedingungen, Menstruationszyklus und Betätigung.



Bitte beachten: Die Stelle und Methode der Messung muss ggf. dem Endverbraucher angezeigt werden, um eine präzise Interpretation der gemessenen Temperatur zu ermöglichen.">
			keywords = <"Temperatur", "Körper", "Kern", "Fieber", "Hypothermie", "Hyperthermie">
			misuse = <"Dieser Archetyp soll nicht benutzt werden, um die Messung der Temperatur irgendeines anderen Objekts zu dokumentieren.



Dieser Archetyp soll nicht benutzt werden, um die Temperatur eines Körperteils isoliert zu messen, z. B. die Temperatur an der Fußsohle im Rahmen des Managements von chronischem Diabetes.">
			copyright = <"© openEHR Foundation">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			purpose = <"Para registrar a temperatura aferida de uma pessoa - com valor médio equivalente para o corpo inteiro.">
			use = <"Usado para registrar a temperatura corporal de uma pessoa ou organismo.
Clusters adicionais podem ser incluídos para fornecer dados adicionais - incluindo as condições ambientais, os detalhes do ciclo menstrual e detalhes de esforço, se for caso.

Observação: O local e método de gravação podem precisar de ser exibidos ao usuário final para facilitar a interpretação exata da temperatura registrada.">
			keywords = <"temperatura", "corpo", "febre", "hipotermia", "hipertermia">
			misuse = <"Esse arquétipo não pode ser usado para registrar a temperatura de qualquer outro objeto.
Esse arquétipo não pode ser usado para registrar a temperatura de uma parte do corpo isoladamente, por exemplo, temperatura da sola do pé, como parte do controle de diabetes crônica.">
			copyright = <"© openEHR Foundation">
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			purpose = <"Для записи измеряемой температуры человека - в качестве суррогата температуры всего тела.">
			use = <"Используется для записи температуры тела пациента или органа.
Дополнительные кластеры могут быть включены для получения дополнительной информации о состоянии - в том числе условия внешней среды, фаза менструального цикла и другие детали, где это уместно.
Обратите внимание: запись о месте и методе измерения  может потребоваться  для облегчения точной интерпретации регистрируемой температуры.">
			keywords = <"температура", "лихорадка", "жар", "гипертермия", "гипотермия">
			misuse = <"Этот архетип не следует использовать для записи температуры любого другого объекта.
Этот архетип не следует использовать для записи температуры части тела, например, отдельного измерения температуры ступни в лечении больных с диабетической стопой.">
			copyright = <"© openEHR Foundation">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			purpose = <"Registrar la temperatura medida de una persona - como un derivado de la temperatura corporal">
			use = <"Usar para registrar la temperatura corporal de una persona o cuerpo.
Clusters adicionales pueden incluirse para proveer datos adicionales de estado - incluyendo condiciones ambientales, detalles del ciclo menstrual y de ejercicio físico, cuando se considera apropiado.
Tener en cuenta: El sitio y el método del registro quizás sea necesario mostrarlo al usuario final, para la adecuada interpretación del registro de temperatura.">
			keywords = <"temperatura", "cuerpo", "central", "fiebre", "hipotermia", "hipertermia">
			misuse = <"Este arquetipo no debe usarse para registrar la temperatura de cualquier otro objeto.
Este arquetipo no debe usarse para registrar la temperatura de una parte del cuerpo aislado por ej: la temperatura de la planta del pie como parte del manejo de la diabetes crónica.">
			copyright = <"© openEHR Foundation">
		>
		["nb"] = <
			language = <[ISO_639-1::nb]>
			purpose = <"Å registrere målt temperatur til en person - med hensikt at den målte temperaturen skal gjenspeile temperaturen den faktiske kroppstemperaturen.

To record the measured temperature of a person - as a surrogate for the temperature of the whole body.(en)">
			use = <"Brukes for å registrere kropptemperatur.
Ekstra clustere kan inkluderes for å sørge for tilleggsdata slik som beskrivelse av omgivelser, menstruasjonssyklus og anstrengelse.
Vær oppmerksom på at metode for måling kan være nødvendig å vise til sluttbrukeren for å gi en korrekt tolkning av den målte temperaturen.

Used for recording the whole body temperature of a person or body.
Additional clusters can be included to provide additional state data - including environmental conditions, menstrual cycle details and exertion details, where appropriate.
Please Note: The site and method of recording may need to be displayed to the end user to facilitate accurate interpretation of the temperature recorded.(en)">
			keywords = <"temperatur", "kropp", "kjerne", "feber", "hypotermi", "hypertermi">
			misuse = <"Arketypen skal ikke brukes for å registrere temperaturen til andre objekter.
Arketypen skal ikke brukes for å registrerer en isolert del av kroppen, som for eksempel temperaturen i fotsålen som del av håndtering av en pasient med kronisk diabetes.

*This archetype is not to be used to record the temperature of any other object.
This archetype is not to be used to record the temperature of a part of the body in isolation e.g. temperature of the sole of the foot as a part of chronic diabetes management.(en)">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"لتسجيل درجة الحرارة التي تم قياسها للشخص - كبديل عن درجة حرارة الجسم كله">
			use = <"يستخدم لتسجيل حرارة جميع الجسم للشخص أو الجثة.
يمكن تضمين عناقيد أخرى للإمداد بالمزيد من تفاصيل الحالة - بما في ذلك العوامل البيئية, تفاصيل الدورة الشهرية, تفاصيل المجهود, حيثما تطلب الأمر.
الرجاء ملاحظة: قد يكون من الواجب عرض هذا الموقع و طريقة التسجيل للمستخدِم النهائي لتسهيل التفسير الدقيق للحرارة التي يتم تسجيلها.">
			keywords = <"الحرارة", "الجسم", "اللُّب", "الحمى", "انخفاض الحرارة", "فرط الحرارة">
			misuse = <"هذا النموذج لا يستخدم لتسجيل حرارة أي شيئ آخر.
هذا النموذج لا يستخدم لتسجيل الحرارة لجزء معزول من الجسم, مثلا حرارة أخمص القدم كجزء من التدبير العلاجي لمرض السكري المزمن.">
			copyright = <"© openEHR Foundation">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			purpose = <"برای ثبت اندازه گیری دمای بدن یک فرد بکار می رود- به عنوان جایگزینی برای دمای کل بدن">
			use = <"برای ثبت دمای کل بدن فرد یا بدن استفاده می شود . خوشه‌های اضافی، برای در بر گرفتن داده‌های حالت بیشتر، شامل شرایط محیطی ، جزییات عادت ماهیانه و جزییات جنب و جوش فرد، هر جا که مناسب باشند، می‌توانند گنجانده شوند.
لطفا توجه داشته باشید که برای تسهیل در تفسیر صحیح دما ثبت شده، توسط کاربر نهایی ممکن است که نمایش محل و روش ثبت لازم باشد">
			keywords = <"دما", "بدن", "مرکز", "تب", "کاهش دمای بدن", "افزایش دمای بدن">
			misuse = <"این الگو ساز جهت ثبت دما اشیا دیگر بکار نمی رود .
این الگو ساز جهت ثبت دمای بخشهایی از بدن -
به عنوان مثال دمای کف پا به عنوان بخشی از پایش دیابت مزمن- بصورت جداگانه استفاده نمی شود
   ">
			copyright = <"© openEHR Foundation">
		>
		["es"] = <
			language = <[ISO_639-1::es]>
			purpose = <"Registrar la temperatura medida de una persona - como un derivado de la temperatura corporal">
			use = <"Usar para registrar la temperatura corporal de una persona o cuerpo.
Clusters adicionales pueden incluirse para proveer datos adicionales de estado - incluyendo condiciones ambientales, detalles del ciclo menstrual y de ejercicio físico, cuando se considera apropiado.
Tener en cuenta: El sitio y el método del registro quizás sea necesario mostrarlo al usuario final, para la adecuada interpretación del registro de temperatura.">
			keywords = <"temperatura", "cuerpo", "central", "fiebre", "hipotermia", "hipertermia">
			misuse = <"Este arquetipo no debe usarse para registrar la temperatura de cualquier otro objeto.
Este arquetipo no debe usarse para registrar la temperatura de una parte del cuerpo aislado por ej: la temperatura de la planta del pie como parte del manejo de la diabetes crónica.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Knut Bernstein", "Sebastian Garde", "Ian McNicoll", "Omer Hotomaroglu", "Sundaresan Jaganathan", "Heather Leslie", "Shahla Foozonkhah">
	other_details = <
		["MD5-CAM-1.0.1"] = <"67AD0398E82C094EA41963065CD85084">
	>

definition
	OBSERVATION[at0000] matches {	-- Körpertemperatur
		data matches {
			HISTORY[at0002] matches {	-- History
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0003] occurrences matches {0..*} matches {	-- Any event
						data matches {
							ITEM_TREE[at0001] matches {	-- Single
								items cardinality matches {1; unordered} matches {
									ELEMENT[at0004] matches {	-- Temperatur
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::127]>
												list = <
													["1"] = <
														units = <"°C">
														precision = <|1|>
													>
													["2"] = <
														units = <"°F">
														precision = <|1|>
													>
												>
											>
										}
									}
								}
							}
						}
						state matches {
							ITEM_TREE[at0029] matches {	-- Status
								items cardinality matches {0..*; ordered} matches {
									ELEMENT[at0030] occurrences matches {0..1} matches {	-- Körperexposition
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0031, 	-- Nackt
													at0032, 	-- Verminderte Kleidung/Bettzeug
													at0033, 	-- Angemessene Kleidung/Bettzeug
													at0034; 	-- Erhöhte Kleidung/Bettzeug
													at0033]	-- assumed value
												}
											}
										}
									}
									allow_archetype CLUSTER[at0056] occurrences matches {0..1} matches {	-- Umgebungsbedingungen
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.environmental_conditions\.v1/}
									}
									allow_archetype CLUSTER[at0057] occurrences matches {0..1} matches {	-- Betätigung
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.level_of_exertion\.v1/}
									}
									allow_archetype ELEMENT[at0058] occurrences matches {0..1} matches {	-- Menstruationszyklus
										include
											archetype_id/value matches {/openEHR-EHR-ELEMENT\.last_normal_menstrual_period\.v1|openEHR-EHR-ELEMENT\.menstrual_cycle_day\.v1/}
									}
									ELEMENT[at0041] occurrences matches {0..1} matches {	-- Beschreibung der Wärmebelastung
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0020] matches {	-- Protocol
				items cardinality matches {0..*; ordered} matches {
					ELEMENT[at0021] occurrences matches {0..1} matches {	-- Messstelle
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0022, 	-- Mund
									at0023, 	-- Ohrenkanal
									at0024, 	-- Achselhöhle
									at0025, 	-- Rektum
									at0026, 	-- Nasopharynx
									at0027, 	-- Harnblase
									at0028, 	-- Intravaskulär
									at0043, 	-- Haut
									at0051, 	-- Vagina
									at0054, 	-- Oesophagus
									at0055]	-- Inguinale Hautfalte
								}
							}
						}
					}
					allow_archetype CLUSTER[at0059] occurrences matches {0..1} matches {	-- Gerät
						include
							archetype_id/value matches {/openEHR-EHR-CLUSTER\.device\.v1/}
					}
				}
			}
		}
	}


ontology
	terminologies_available = <"LNC205", ...>
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Body temperature">
					description = <"A measurement of the body temperature, which is a surrogate for the whole body temperature of the person.">
				>
				["at0001"] = <
					text = <"Single">
					description = <"*">
				>
				["at0002"] = <
					text = <"History">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"Any event">
					description = <"Any event">
				>
				["at0004"] = <
					text = <"Temperature">
					description = <"The measured body temperature (as a surrogate for the whole body).">
				>
				["at0020"] = <
					text = <"Protocol">
					description = <"@ internal @">
				>
				["at0021"] = <
					text = <"Site of measurement">
					description = <"The anatomical site of measurement of the temperature.">
				>
				["at0022"] = <
					text = <"Mouth">
					description = <"Temperature is measured within the mouth.">
				>
				["at0023"] = <
					text = <"Ear canal">
					description = <"Temperature is measured from within the external auditory canal.">
				>
				["at0024"] = <
					text = <"Axilla">
					description = <"Temperature is measured from the skin of the axilla with the arm positioned down by the side.">
				>
				["at0025"] = <
					text = <"Rectum">
					description = <"Temperature measured within the rectum.">
				>
				["at0026"] = <
					text = <"Nasopharynx">
					description = <"Temperature is measured within the nasopharynx.">
				>
				["at0027"] = <
					text = <"Urinary bladder">
					description = <"Temperature is measured in the urinary bladder.">
				>
				["at0028"] = <
					text = <"Intravascular">
					description = <"Temperature is measured within the vascular system.">
				>
				["at0029"] = <
					text = <"State">
					description = <"State information about the patient.">
				>
				["at0030"] = <
					text = <"Body exposure">
					description = <"The thermal situation of the person who is having the temperature taken.">
				>
				["at0031"] = <
					text = <"Naked">
					description = <"No clothing, bedding or covering.">
				>
				["at0032"] = <
					text = <"Reduced clothing/bedding">
					description = <"The person is covered by a lesser amount of clothing or bedding than deemed appropriate for the environmental circumstances.">
				>
				["at0033"] = <
					text = <"Appropriate clothing/bedding">
					description = <"The person is covered by an amount of clothing or bedding deemed appropriate for the environmental circumstances.">
				>
				["at0034"] = <
					text = <"Increased clothing/bedding">
					description = <"The person is covered by an increased amount of clothing or bedding than deemed appropriate for the environmental circumstances.">
				>
				["at0041"] = <
					text = <"Description of thermal stress">
					description = <"Description of the conditions applied to the subject that might influence their measured body temperature.">
				>
				["at0043"] = <
					text = <"Skin">
					description = <"Temperature is measured from exposed skin.">
				>
				["at0051"] = <
					text = <"Vagina">
					description = <"Temperature is measured within the vagina.">
				>
				["at0054"] = <
					text = <"Oesophagus">
					description = <"Temperatue is measured within the oesophagus.">
				>
				["at0055"] = <
					text = <"Inguinal skin crease">
					description = <"Temperature is measured in the inguinal skin crease between the leg and abdominal wall.">
				>
				["at0056"] = <
					text = <"Environmental Conditions">
					description = <"Details about the environmental conditions at the time of temperature measurement.">
				>
				["at0057"] = <
					text = <"Exertion">
					description = <"Details about the exertion of the person at the time of temperature measurement.">
				>
				["at0058"] = <
					text = <"Menstrual Cycle">
					description = <"Details about the menstrual cycle of a woman.">
				>
				["at0059"] = <
					text = <"Device">
					description = <"Details about the device use to measure body temperature.">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"Körpertemperatur">
					description = <"Eine Messung der Körpertemperatur an einer bestimmten Stelle als Surrogat für den gesamten Körper der Person.">
				>
				["at0001"] = <
					text = <"Single">
					description = <"*">
				>
				["at0002"] = <
					text = <"History">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"Any event">
					description = <"Any event.">
				>
				["at0004"] = <
					text = <"Temperatur">
					description = <"Die gemessene Körpertemperatur (als Surrogat für den gesamten Körper).">
				>
				["at0020"] = <
					text = <"Protocol">
					description = <"@ internal @">
				>
				["at0021"] = <
					text = <"Messstelle">
					description = <"Die anatomische Stelle der Temperaturmessung.">
				>
				["at0022"] = <
					text = <"Mund">
					description = <"Messung der Temperatur im Mund.">
				>
				["at0023"] = <
					text = <"Ohrenkanal">
					description = <"Messung der Temperatur innerhalb des äußeren Gehörgangs.">
				>
				["at0024"] = <
					text = <"Achselhöhle">
					description = <"Messung der Temperatur an der Haut der Achselhöhle mit seitlich angelegtem Arm.">
				>
				["at0025"] = <
					text = <"Rektum">
					description = <"Messung der Temperatur innerhalb des Rektums.">
				>
				["at0026"] = <
					text = <"Nasopharynx">
					description = <"Messung der Temperatur innerhalb des Nasopharynxs (Nasenrachens).">
				>
				["at0027"] = <
					text = <"Harnblase">
					description = <"Messung der Temperatur in der Harnblase.">
				>
				["at0028"] = <
					text = <"Intravaskulär">
					description = <"Messung der Temperatur innerhalb des vaskulären Systems.">
				>
				["at0029"] = <
					text = <"Status">
					description = <"Statusinformationen über die Person.">
				>
				["at0030"] = <
					text = <"Körperexposition">
					description = <"Die thermale Situation der Person, deren Temperatur gemessen wird.">
				>
				["at0031"] = <
					text = <"Nackt">
					description = <"Keine Kleidung, Bettzeug oder andere Bedeckung.">
				>
				["at0032"] = <
					text = <"Verminderte Kleidung/Bettzeug">
					description = <"Die Person wird bedeckt von einer geringeren Menge an Kleidung oder Bettzeug als für die Umgebungsbedingungen angemessen erscheint.">
				>
				["at0033"] = <
					text = <"Angemessene Kleidung/Bettzeug">
					description = <"Die Person wird bedeckt von einer Menge an Kleidung oder Bettzeug, die den Umgebungsbedingungen angemessen erscheint.">
				>
				["at0034"] = <
					text = <"Erhöhte Kleidung/Bettzeug">
					description = <"Die Person wird bedeckt von einer größeren Menge an Kleidung oder Bettzeug als für die Umgebungsbedingungen angemessen erscheint.">
				>
				["at0041"] = <
					text = <"Beschreibung der Wärmebelastung">
					description = <"Beschreibung von Bedingungen, denen die Person ausgesetzt ist, welche die gemessene Körpertemperatur beeinflussen könnten.">
				>
				["at0043"] = <
					text = <"Haut">
					description = <"Messung der Temperatur an freiliegender Haut.">
				>
				["at0051"] = <
					text = <"Vagina">
					description = <"Messung der Temperatur innerhalb der Vagina.">
				>
				["at0054"] = <
					text = <"Oesophagus">
					description = <"Messung der Temperatur innerhalb des Oesophagus.">
				>
				["at0055"] = <
					text = <"Inguinale Hautfalte">
					description = <"Messung der Temperatur in der inguinalen Hautfalte zwischen Bein und Abdominalwand.">
				>
				["at0056"] = <
					text = <"Umgebungsbedingungen">
					description = <"Details über die Umgebungsbedingungen zur Zeit der Messung.">
				>
				["at0057"] = <
					text = <"Betätigung">
					description = <"Details über die Betätigung der Person zum Zeitpunkt der Messung der Temperatur.">
				>
				["at0058"] = <
					text = <"Menstruationszyklus">
					description = <"Details über den Menstruationszyklus einer Frau.">
				>
				["at0059"] = <
					text = <"Gerät">
					description = <"Details über das Gerät, das zur Temperaturmessung benutzt wurde.">
				>
			>
		>
		["pt-br"] = <
			items = <
				["at0000"] = <
					text = <"Temperatura Corporal">
					description = <"O valor para a temperatura corporal, com valor médio equivalente para o corpo inteiro.">
				>
				["at0001"] = <
					text = <"Single">
					description = <"*">
				>
				["at0002"] = <
					text = <"History">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"Qualquer evento">
					description = <"Qualquer evento.">
				>
				["at0004"] = <
					text = <"Temperatura">
					description = <"A temperatura corporal aferida (média para o corpo inteiro).">
				>
				["at0020"] = <
					text = <"Protocol">
					description = <"@ internal @">
				>
				["at0021"] = <
					text = <"Local da medida">
					description = <"O local anatômico de onde a temperatura foi aferida.">
				>
				["at0022"] = <
					text = <"Boca">
					description = <"A temperatura é eferida no interior da boca.">
				>
				["at0023"] = <
					text = <"Canal auditivo">
					description = <"A temperatura é aferida dentro do canal auditivo do ouvido externo (conduto auditivo).">
				>
				["at0024"] = <
					text = <"Axilla">
					description = <"A temperatura é aferida na pele da axila com o braço abaixado.">
				>
				["at0025"] = <
					text = <"Reto">
					description = <"A temperatura é aferida no reto.">
				>
				["at0026"] = <
					text = <"Nasofaringe">
					description = <"A temperatura é aferida na parte nasal da faringe.">
				>
				["at0027"] = <
					text = <"Bexiga">
					description = <"A temperatura é aferida na bexiga.">
				>
				["at0028"] = <
					text = <"Intravascular">
					description = <"A temperatura é aferida no sistema vascular.">
				>
				["at0029"] = <
					text = <"Estado">
					description = <"Informações sobre o estado do paciente.">
				>
				["at0030"] = <
					text = <"Exposição do corpo">
					description = <"A situação térmica da pessoa que tem a sua temperatura aferida.">
				>
				["at0031"] = <
					text = <"Despido">
					description = <"Sem roupas, camisola ou capa.">
				>
				["at0032"] = <
					text = <"Vestuário reduzido/camisola">
					description = <"A pessoa está vestida por pouca roupa ou camisola considerado o vestuário necessário para as circunstâncias ambientais.">
				>
				["at0033"] = <
					text = <"Apropriadamente vestido">
					description = <"A pessoa está vestida apropriadamente considerado o vestuário necessário para as circunstâncias ambientais.">
				>
				["at0034"] = <
					text = <"Excessivamente vestido">
					description = <"A pessoa está excessivamente vestida considerado o vestuário necessário para as circunstâncias ambientais.">
				>
				["at0041"] = <
					text = <"Choque térmico">
					description = <"Descrição das condições aplicadas ao sujeito que possa influenciar a medida de sua temperatura corporal.">
				>
				["at0043"] = <
					text = <"Pele">
					description = <"A temperatura é aferida a partir da pele exposta.">
				>
				["at0051"] = <
					text = <"Vagina">
					description = <"A temperatura é afereida no interior da vagina.">
				>
				["at0054"] = <
					text = <"Esófago">
					description = <"A temperatura é aferida no esófago.">
				>
				["at0055"] = <
					text = <"Região Inguinal">
					description = <"A temperatura é aferida na dobra da pele entre a região inguinal e a região abdominal.">
				>
				["at0056"] = <
					text = <"Condições ambientais">
					description = <"Detalhes sobre as condições ambientais no momento em que foi aferida a temperatura.">
				>
				["at0057"] = <
					text = <"Esforço">
					description = <"Detalhes sobre esforço que a pessoa fez no momento da aferição da temperatura.">
				>
				["at0058"] = <
					text = <"Ciclo Menstrual">
					description = <"Detalhes sobre o ciclo menstrual da mulher.">
				>
				["at0059"] = <
					text = <"Dispositivo">
					description = <"Detalhes sobre o dispositivo utilizado para medir a temperatura corporal.">
				>
			>
		>
		["ru"] = <
			items = <
				["at0000"] = <
					text = <"Температура тела">
					description = <"Измерение температуры тела, которая является суррогатом температуры тела человека в целом.">
				>
				["at0001"] = <
					text = <"*Single(en)">
					description = <"**(en)">
				>
				["at0002"] = <
					text = <"*History(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"Любое событие">
					description = <"Любое событие.">
				>
				["at0004"] = <
					text = <"Температура(ru)">
					description = <"Измеряется температура тела (как суррогат для всего тела).">
				>
				["at0020"] = <
					text = <"*Protocol(en)">
					description = <"*@ internal @(en)">
				>
				["at0021"] = <
					text = <"Место измерения">
					description = <"Анатомическое место измернеия температуры.">
				>
				["at0022"] = <
					text = <"Рот">
					description = <"Температура измеряется в ротовой полости.">
				>
				["at0023"] = <
					text = <"Наружный слуховой проход">
					description = <"Температура измеряется в наружном слуховом проходе.">
				>
				["at0024"] = <
					text = <"Подмышечная впадина">
					description = <"Температура измеряется в кожной складке в подмышечной впадине, рука опущена вниз и прижата к туловищу.">
				>
				["at0025"] = <
					text = <"Прямая кишка">
					description = <"Температура измеряется внутри прямой кишки.">
				>
				["at0026"] = <
					text = <"Носоглотка">
					description = <"Температура измеряется в носоглотке.">
				>
				["at0027"] = <
					text = <"Мочевой пузырь">
					description = <"Температура измеряется внутри мочевого пузыря.">
				>
				["at0028"] = <
					text = <"Внутрисосудистая">
					description = <"Температура измеряется внутри сосоудистого русла.">
				>
				["at0029"] = <
					text = <"Состояние">
					description = <"Информация о состоянии пациента.">
				>
				["at0030"] = <
					text = <"*Body exposure(en)">
					description = <"*The thermal situation of the person who is having the temperature taken(en)">
				>
				["at0031"] = <
					text = <"Обнажён">
					description = <"Без одежды, ничем не укрыт.">
				>
				["at0032"] = <
					text = <"Лёгкая одежда/постель">
					description = <"На пациенте меньшее количество одежды / постельных принадлежностей, чем этого требуют условия внешней среды.">
				>
				["at0033"] = <
					text = <"Соответствующая одежда/постель">
					description = <"Одежда/постельные принадлежности пациента соответствуют условиям внешней среды.">
				>
				["at0034"] = <
					text = <"Теплая одежда/постель">
					description = <"На пациенте большее количество одежды / постельных принадлежностей, чем этого требуют условия внешней среды.">
				>
				["at0041"] = <
					text = <"Тепловой стресс">
					description = <"Описание особенностей, которые могут повлиять на результат измерения температуры тела.">
				>
				["at0043"] = <
					text = <"Кожа">
					description = <"Температура измеряется на поверхности кожи.">
				>
				["at0051"] = <
					text = <"Влагалище">
					description = <"Температура измеряется внутри влагвалища.">
				>
				["at0054"] = <
					text = <"Пищевод">
					description = <"Температура измеряется внитри пищевода.">
				>
				["at0055"] = <
					text = <"Паховая складка">
					description = <"Температура измеряется в паховой складке кожи между ногой и передней брюшной стенкой.">
				>
				["at0056"] = <
					text = <"Условия внешней среды">
					description = <"Подробная информация об условиях внешней среды в момент изменения температуры.">
				>
				["at0057"] = <
					text = <"Нагрузка">
					description = <"Подробная информация о нагрузках в момент измерения температуры.">
				>
				["at0058"] = <
					text = <"Менструальный цикл">
					description = <"Информация о фазе менструального цикла у женщины.">
				>
				["at0059"] = <
					text = <"Устройство">
					description = <"Информация об устройстве, используемом для измерения температуры тела.">
				>
			>
		>
		["es-ar"] = <
			items = <
				["at0000"] = <
					text = <"Temperatura Corporal">
					description = <"La medición de la temperatura corporal, que deriva en la temperatura de todo el cuerpo de una persona.">
				>
				["at0001"] = <
					text = <"Aislado">
					description = <"Registro aislado de la temperatura.">
				>
				["at0002"] = <
					text = <"*History(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"Cualquier evento">
					description = <"Cualquier evento">
				>
				["at0004"] = <
					text = <"Temperatura">
					description = <"La temperatura corporal medida (representa la temperatura de todo el cuerpo).">
				>
				["at0020"] = <
					text = <"*Protocol(en)">
					description = <"*@ internal @(en)">
				>
				["at0021"] = <
					text = <"Sitio de la medición">
					description = <"El sitio anatómico donde se mide la temperatura.">
				>
				["at0022"] = <
					text = <"Boca">
					description = <"Temperatura bucal.">
				>
				["at0023"] = <
					text = <"Canal auditivo">
					description = <"La temperatura se mide en el canal auditivo externo.">
				>
				["at0024"] = <
					text = <"Axila">
					description = <"La temperatura se mide en el hueco axilar con el brazo posicionado al costado del cuerpo.">
				>
				["at0025"] = <
					text = <"Recto">
					description = <"Temperatura rectal.">
				>
				["at0026"] = <
					text = <"Nasofaríngeo">
					description = <"La temperatura se mide dentro de la nasofaringe.">
				>
				["at0027"] = <
					text = <"Vejiga urinaria">
					description = <"La temperatura se mide en la vejiga urinaria.">
				>
				["at0028"] = <
					text = <"Intravascular">
					description = <"La temperatura se mide dentro del sistema vascular.">
				>
				["at0029"] = <
					text = <"Estado">
					description = <"Estado de la información del paciente.">
				>
				["at0030"] = <
					text = <"Exposición corporal">
					description = <"La situación térmica de la persona al cual se le registra la temperatura.">
				>
				["at0031"] = <
					text = <"Desnudo">
					description = <"Sin ropas, sabanas o coberturas.">
				>
				["at0032"] = <
					text = <"Ropas/lecho reducidas">
					description = <"La persona esta cubierto por una cantidad menor de ropas o sabanas que lo considerado apropiado para las circunstancias ambientales.">
				>
				["at0033"] = <
					text = <"Ropas/lecho apropiadas">
					description = <"La persona esta cubierta por una adecuada cantidad de ropas o sabanas, que lo considerado apropiado para las circunstancias ambientales.">
				>
				["at0034"] = <
					text = <"Ropas/lecho aumentado">
					description = <"La persona se encuentra cubierto por una cantidad incrementada de ropas o sabanas que lo considerado apropiado para las circunstancias ambientales.">
				>
				["at0041"] = <
					text = <"Descripción de estrés térmico">
					description = <"Descripción de las condiciones que le suceden al sujeto que puede influenciar la temperatura corporal medida.">
				>
				["at0043"] = <
					text = <"Piel">
					description = <"La temperatura se mide sobre la piel expuesta.">
				>
				["at0051"] = <
					text = <"Vagina">
					description = <"Temperatura vaginal.">
				>
				["at0054"] = <
					text = <"Esófago">
					description = <"Temperatura se mide dentro del esófago.">
				>
				["at0055"] = <
					text = <"Pliegue inguinal">
					description = <"La temperatura se mide en el pliegue inguinal entre el muslo y la pared abdominal.">
				>
				["at0056"] = <
					text = <"Condiciones Ambientales">
					description = <"Detalles de las condiciones ambientales al momento del registro de la temperatura.">
				>
				["at0057"] = <
					text = <"Ejercicio">
					description = <"Detalles sobre la actividad física de la persona al momento de la medición de la temperatura.">
				>
				["at0058"] = <
					text = <"Ciclo Menstrual">
					description = <"Detalles sobre el ciclo menstrual de la mujer.">
				>
				["at0059"] = <
					text = <"Dispositivo">
					description = <"Detalles sobre el dispositivo usado para medir la temperatura corporal.">
				>
			>
		>
		["nb"] = <
			items = <
				["at0000"] = <
					text = <"Kroppstemperatur">
					description = <"Måling av kroppstemperatur som skal gjenspeile den faktiske kroppstemperaturen">
				>
				["at0001"] = <
					text = <"*Single(en)">
					description = <"**(en)">
				>
				["at0002"] = <
					text = <"*History(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"Tidfestet hendelse">
					description = <"En tidfestet hendelse">
				>
				["at0004"] = <
					text = <"Temperatur">
					description = <"Målt kroppstemperatur (som gjenspeiler faktisk kroppstemperatur) ">
				>
				["at0020"] = <
					text = <"*Protocol(en)">
					description = <"*@ internal @(en)">
				>
				["at0021"] = <
					text = <"Anatomisk målested">
					description = <"Det anatomiske målestedet for måling av temperatur ">
				>
				["at0022"] = <
					text = <"Munn">
					description = <"Temperatur målt i munnhulen ">
				>
				["at0023"] = <
					text = <"Øre">
					description = <"Temperatur målt i den ytre ørekanalen ">
				>
				["at0024"] = <
					text = <"Aksille">
					description = <"Temperatur er målt i aksille når armen er posisjonert ned langs siden">
				>
				["at0025"] = <
					text = <"Rektum">
					description = <"Temperatur målt i rektum">
				>
				["at0026"] = <
					text = <"Nasofarynks">
					description = <"Temperatur målt i nasofarynks">
				>
				["at0027"] = <
					text = <"Urinblære">
					description = <"Temperatur målt i urinblære">
				>
				["at0028"] = <
					text = <"Intravaskulært">
					description = <"Temperatur målt intravaskulært">
				>
				["at0029"] = <
					text = <"*State(en)">
					description = <"*State information about the patient.(en)">
				>
				["at0030"] = <
					text = <"*Body exposure(en)">
					description = <"*The thermal situation of the person who is having the temperature taken.(en)">
				>
				["at0031"] = <
					text = <"Naken">
					description = <"Ingen klær eller tildekking">
				>
				["at0032"] = <
					text = <"Redusert bekledning/tildekking">
					description = <"Personen er mindre kledt eller tildekket enn omgivelsene skulle tilsi">
				>
				["at0033"] = <
					text = <"Passende bekleding/tildekking">
					description = <"Personen er passende kledt eller tildekket i forhold til omgivelsene">
				>
				["at0034"] = <
					text = <"Økt bekledning/tildekking">
					description = <"Personen er mer kledt eller tildekket enn omgivelsene skulle tilsi">
				>
				["at0041"] = <
					text = <"Tilført temperaturpåvirkning">
					description = <"Temperaturpåvirkning tilført pasienten for å oppnå en økning eller reduksjon i kroppstemperatur.">
				>
				["at0043"] = <
					text = <"Hud">
					description = <"Temperaturen mål i eksponert hud">
				>
				["at0051"] = <
					text = <"Vagina">
					description = <"Temperatur målt i vagina">
				>
				["at0054"] = <
					text = <"Øsofagus">
					description = <"Temperatur målt i øsofagus">
				>
				["at0055"] = <
					text = <"Inguinalt">
					description = <"Temperatur målt inguinalt når overeksremitet ligger mot abdomen">
				>
				["at0056"] = <
					text = <"Omgivelser">
					description = <"Detaljer om omgivelsene når temperatur ble målt">
				>
				["at0057"] = <
					text = <"Anstrengelse">
					description = <"Detaljer om anstrengelse/aktivitet hos personen når temperaturen ble målt">
				>
				["at0058"] = <
					text = <"Menstruasjonssyklus">
					description = <"Detaljer om menstruasjonssyklus">
				>
				["at0059"] = <
					text = <"Måleinstrument">
					description = <"Detaljer om måleinstrument som ble brukt til å måle temperaturen">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"درجة حرارة الجسم">
					description = <"قياس لدرجة حرارة الجسم, و التي تحل كبديل لدرجة الحرارة الكلية لجسم الشخص">
				>
				["at0001"] = <
					text = <"مُفرَد">
					description = <"*">
				>
				["at0002"] = <
					text = <"*History(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"إحدى الوقائع">
					description = <"إحدى الوقائع">
				>
				["at0004"] = <
					text = <"درجة الحرارة">
					description = <"درجة الحرارة التي تم قياسها - كبديل عن الجسم الكلي">
				>
				["at0020"] = <
					text = <"*Protocol(en)">
					description = <"*@ internal @(en)">
				>
				["at0021"] = <
					text = <"موضع القياس">
					description = <"الموضع التشريحي الذي يتم فيه قياس درجة الحرارة">
				>
				["at0022"] = <
					text = <"الفم">
					description = <"يتم قياس الحرارة في داخل الفم">
				>
				["at0023"] = <
					text = <"قناة الأذن">
					description = <"يتم قياس درجة الحرارة من داخل القناة السمعية الخارجية">
				>
				["at0024"] = <
					text = <"الإبط">
					description = <"يتم قياس درجة الحرارة من بشرة/ جلد الإبط في حالة وضع الذراع جانبا و هو متجه إلى أسفل">
				>
				["at0025"] = <
					text = <"المستقيم">
					description = <"درجة الحرارة التي يتم قياسها في داخل المستقيم">
				>
				["at0026"] = <
					text = <"البلعوم الأنفي">
					description = <"درجة الحرارة التي يتم قياسها من داخل البلعوم الأنفي">
				>
				["at0027"] = <
					text = <"المثانة البولية ">
					description = <"يتم قياس درجة الحرارة من داخل المثانة البولية">
				>
				["at0028"] = <
					text = <"داخل الأوعية الدموية">
					description = <"يتم قياس درجة الحرارة من داخل الجهاز الدوري - الأوعية الدموية">
				>
				["at0029"] = <
					text = <"الحالة">
					description = <"معلومات حول حالة المريض">
				>
				["at0030"] = <
					text = <"تَعَرُّض الجسم">
					description = <"الموقف الحراري للشخص الذي يتم قياس درجة حرارته">
				>
				["at0031"] = <
					text = <"مُعرَّى">
					description = <"لا يوجد ملابس أو شراشف أو غطاء">
				>
				["at0032"] = <
					text = <"ملابس/ شراشف خفيفة">
					description = <"الشخص مُغَطَّى بكمية من الملابس أو الشراشف أقل من تلك المناسبة للظروف البيئية المحيطة">
				>
				["at0033"] = <
					text = <"ملابس/شراشف مناسبة">
					description = <"الشخص مُغَطَّى بكمية من الملابس أو الشراشف المناسبة للظروف البيئية المحيطة">
				>
				["at0034"] = <
					text = <"ملابس/شراشف زائدة">
					description = <"الشخص مُغَطَّى بكمية زائدة من الملابس/ الشراشف المناسبة للظروف البيئية المحيطة">
				>
				["at0041"] = <
					text = <"وصف الضغط الحرارة">
					description = <"وصف للظروف المُطبَّقة على المريض و التي قد تؤثر على درجة الحرارة التي يتم قياسها">
				>
				["at0043"] = <
					text = <"الجلد/ البشرة">
					description = <"يتم قياس درجة الحرارة من الجلد المُعَرَّض/ المكشوف">
				>
				["at0051"] = <
					text = <"المهبل">
					description = <"يتم قياس درجة الحرارة من داخل المهبل">
				>
				["at0054"] = <
					text = <"المريئ">
					description = <"يتم قياس درجة الحرارة من داخل المريئ">
				>
				["at0055"] = <
					text = <"غضن الجلد عند الأربتين">
					description = <"يتم قياس درجة الحرارة عند غضن الجلد بين الأربتين - بين الرجل و جدار البطن">
				>
				["at0056"] = <
					text = <"الظروف البيئية">
					description = <"تفاصيل حول الظروف البيئية في وقت قياس درجة الحرارة">
				>
				["at0057"] = <
					text = <"المجهود">
					description = <"تفاصيل حول المجهود الذي يقوم به الشخص في وقت قياس درجة الحرارة">
				>
				["at0058"] = <
					text = <"دورة الحيض">
					description = <"تفاصيل حول دورة الحيض لدى المرأة">
				>
				["at0059"] = <
					text = <"الجهيزة">
					description = <"تفاصيل حول الجهيزة المستخدمة لقياس درجة حرارة الجسم">
				>
			>
		>
		["fa"] = <
			items = <
				["at0000"] = <
					text = <"دمای بدن">
					description = <"اندازه گیری دمای بدن که جایگزینی برای دمای کل بدن فرد است">
				>
				["at0001"] = <
					text = <"منفرد">
					description = <"*">
				>
				["at0002"] = <
					text = <"*History(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"هر رویداد">
					description = <"هر رویداد">
				>
				["at0004"] = <
					text = <"دما">
					description = <"دمای اندازه گیری شده از بدن (به عنوان جایگزینی برای کل بدن)٬">
				>
				["at0020"] = <
					text = <"*Protocol(en)">
					description = <"*@ internal @(en)">
				>
				["at0021"] = <
					text = <"محل اندازه گیری">
					description = <"محل آناتومیکی اندازه گیری دمای بدن">
				>
				["at0022"] = <
					text = <"ماه">
					description = <"دما در عرض یک ماه اندازه گیری می شود">
				>
				["at0023"] = <
					text = <"کانال گوش">
					description = <"دما از طریق کانال شنوایی خارجی اندازه گیری می شود">
				>
				["at0024"] = <
					text = <"زیر بغل">
					description = <"دما از طریق پوستی و در زیر بغل، بصورتی که بازو پایین و در کنار بدن باشد، اندازه گیری می شود">
				>
				["at0025"] = <
					text = <"مقعد">
					description = <"دما از طریق مقعد اندازه گیری می شود">
				>
				["at0026"] = <
					text = <"بینی حلقی">
					description = <"دما از طریق بینی حلقی اندازه گیری می شود">
				>
				["at0027"] = <
					text = <"مثانه">
					description = <"دما از طریق مثانه اندازه گیری می شود">
				>
				["at0028"] = <
					text = <"داخل عروقی">
					description = <"دما از طریق سیستم عروقی اندازه گیری می شود">
				>
				["at0029"] = <
					text = <"حالت">
					description = <"اطلاعات حالت بیمار">
				>
				["at0030"] = <
					text = <"نحوه پوشش بدن">
					description = <"وضعیت گرمایی (به لحاظ پوشش) فردی که دمایش گرفته شده است">
				>
				["at0031"] = <
					text = <"لخت">
					description = <"بدون لباس ، ملافه و یا پوشش
">
				>
				["at0032"] = <
					text = <" لباس و یا ملافه کم">
					description = <"فرد با مقدار لباس و یا ملافه کمتر از حد مناسب با شرایط محیطی پوشانده شده است">
				>
				["at0033"] = <
					text = <"لباس یا ملافه مناسب">
					description = <"فرد با لباس و یا ملافه مناسب با شرایط محیطی پوشانده شده است">
				>
				["at0034"] = <
					text = <"لباس و یا ملافه زیاد">
					description = <"فرد با مقدار لباس و یا ملافه بیشتر از حد مناسب با شرایط محیطی پوشانده شده است">
				>
				["at0041"] = <
					text = <"توصیف استرسهای گرمایی">
					description = <"توصیف شرایط اعمال شده به شخص که ممکن است اندازه گیری دمای بدن فرد را تحت تاثیر قرار دهد">
				>
				["at0043"] = <
					text = <"پوست">
					description = <"دما از طریق پوست بدن اندازه گیری می شود">
				>
				["at0051"] = <
					text = <"مهبل">
					description = <"دما از  طریق داخل مهبل اندازه گیری می شود">
				>
				["at0054"] = <
					text = <"مری">
					description = <"دما از طریق داخل مری اندازه گیری می شود">
				>
				["at0055"] = <
					text = <"چین پوستی کشاله رانی">
					description = <"دما از طریق چین پوستی کشاله ران بین ران و دیواره شکم اندازه گیری می شود">
				>
				["at0056"] = <
					text = <"شرایط محیطی">
					description = <"جزییاتی در مورد شرایط محیطی در زمان اندازه گیری دما ">
				>
				["at0057"] = <
					text = <"جنب و جوش">
					description = <"جزییاتی در مورد جنب و جوش  فرد در زمان اندازه گیری دما ">
				>
				["at0058"] = <
					text = <"عادت ماهیانه">
					description = <"جزییاتی در مورد عادت ماهیانه زنان ">
				>
				["at0059"] = <
					text = <"تجهیز">
					description = <"جزییاتی در موردتجهیزات استفاده شده در اندازه گیری دمای بدن">
				>
			>
		>
		["es"] = <
			items = <
				["at0000"] = <
					text = <"Temperatura Corporal">
					description = <"La medición de la temperatura corporal, que deriva en la temperatura de todo el cuerpo de una persona.">
				>
				["at0001"] = <
					text = <"Aislado">
					description = <"Registro aislado de la temperatura.">
				>
				["at0002"] = <
					text = <"*History(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"Cualquier evento">
					description = <"Cualquier evento">
				>
				["at0004"] = <
					text = <"Temperatura">
					description = <"La temperatura corporal medida (representa la temperatura de todo el cuerpo).">
				>
				["at0020"] = <
					text = <"*Protocol(en)">
					description = <"*@ internal @(en)">
				>
				["at0021"] = <
					text = <"Sitio de la medición">
					description = <"El sitio anatómico donde se mide la temperatura.">
				>
				["at0022"] = <
					text = <"Boca">
					description = <"Temperatura bucal.">
				>
				["at0023"] = <
					text = <"Canal auditivo">
					description = <"La temperatura se mide en el canal auditivo externo.">
				>
				["at0024"] = <
					text = <"Axila">
					description = <"La temperatura se mide en el hueco axilar con el brazo posicionado al costado del cuerpo.">
				>
				["at0025"] = <
					text = <"Recto">
					description = <"Temperatura rectal.">
				>
				["at0026"] = <
					text = <"Nasofaríngeo">
					description = <"La temperatura se mide dentro de la nasofaringe.">
				>
				["at0027"] = <
					text = <"Vejiga urinaria">
					description = <"La temperatura se mide en la vejiga urinaria.">
				>
				["at0028"] = <
					text = <"Intravascular">
					description = <"La temperatura se mide dentro del sistema vascular.">
				>
				["at0029"] = <
					text = <"Estado">
					description = <"Estado de la información del paciente.">
				>
				["at0030"] = <
					text = <"Exposición corporal">
					description = <"La situación térmica de la persona al cual se le registra la temperatura.">
				>
				["at0031"] = <
					text = <"Desnudo">
					description = <"Sin ropas, sabanas o coberturas.">
				>
				["at0032"] = <
					text = <"Ropas/lecho reducidas">
					description = <"La persona esta cubierto por una cantidad menor de ropas o sabanas que lo considerado apropiado para las circunstancias ambientales.">
				>
				["at0033"] = <
					text = <"Ropas/lecho apropiadas">
					description = <"La persona esta cubierta por una adecuada cantidad de ropas o sabanas, que lo considerado apropiado para las circunstancias ambientales.">
				>
				["at0034"] = <
					text = <"Ropas/lecho aumentado">
					description = <"La persona se encuentra cubierto por una cantidad incrementada de ropas o sabanas que lo considerado apropiado para las circunstancias ambientales.">
				>
				["at0041"] = <
					text = <"Descripción de estrés térmico">
					description = <"Descripción de las condiciones que le suceden al sujeto que puede influenciar la temperatura corporal medida.">
				>
				["at0043"] = <
					text = <"Piel">
					description = <"La temperatura se mide sobre la piel expuesta.">
				>
				["at0051"] = <
					text = <"Vagina">
					description = <"Temperatura vaginal.">
				>
				["at0054"] = <
					text = <"Esófago">
					description = <"Temperatura se mide dentro del esófago.">
				>
				["at0055"] = <
					text = <"Pliegue inguinal">
					description = <"La temperatura se mide en el pliegue inguinal entre el muslo y la pared abdominal.">
				>
				["at0056"] = <
					text = <"Condiciones Ambientales">
					description = <"Detalles de las condiciones ambientales al momento del registro de la temperatura.">
				>
				["at0057"] = <
					text = <"Ejercicio">
					description = <"Detalles sobre la actividad física de la persona al momento de la medición de la temperatura.">
				>
				["at0058"] = <
					text = <"Ciclo Menstrual">
					description = <"Detalles sobre el ciclo menstrual de la mujer.">
				>
				["at0059"] = <
					text = <"Dispositivo">
					description = <"Detalles sobre el dispositivo usado para medir la temperatura corporal.">
				>
			>
		>
	>
	term_bindings = <
		["LNC205"] = <
			items = <
				["/data[at0002]/events[at0003]/data[at0001]/items[at0004]"] = <[LNC205::8310-5]>
			>
		>
	>

```

Body Weight (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.body_weight.v1

concept
	[at0000]	-- Body weight
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Sebastian Garde, Jasmin Buck">
				["organisation"] = <"Ocean Informatics, University of Heidelberg">
			>
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
				["email"] = <"monasaleh01@live.com">
			>
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			author = <
				["name"] = <"Shahla Foozonkhah">
				["organisation"] = <"Ocean Informatics">
				["email"] = <"Shahla.foozonkhah@oceaninformatics.com">
			>
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			author = <
				["name"] = <"Igor Lizunov">
				["email"] = <"i.lizunov@infinnity.ru">
			>
		>
		["es"] = <
			language = <[ISO_639-1::es]>
			author = <
				["name"] = <"Jose Fernandez-Engo">
				["organisation"] = <"Andalusian Healthcare Ministry - IT Division">
				["email"] = <"joser.fernandez.exts@juntadeandalucia.es">
			>
			accreditation = <"Responsible IOP Estrategy">
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			author = <
				["name"] = <"Marja Buur">
				["organisation"] = <"Medisch Centrum Alkmaar, Nederland">
				["email"] = <"m.buur-krom@mca.nl">
			>
			accreditation = <"Nurse informatics">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			author = <
				["name"] = <"Marco Borges">
				["organisation"] = <"P2D">
				["email"] = <"marco.borges@p2d.com.br">
			>
			accreditation = <"P2D Health Advisor Council">
		>
	>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"2006-03-09">
	>
	details = <
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			purpose = <"Para registrar o peso corporal de um indivíduo - tanto real como aproximado.">
			use = <"Usado para gravar a medição real de peso corporal, inclusive quando o indivíduo tem faltando uma parte do corpo devido a uma causa congênita ou após a remoção cirúrgica. A indicação da imperfeição física do corpo pode ser registrada no elemento 'fatores de erro', se necessário.
Este é o arquétipo para ser utilizado para uma medição típica de peso, por exemplo, auto-medido pelo indivíduo em casa, uma medida médico em uma clínica / hospital, ou um instrutor de fitness em um ginásio. 

Também pode ser usado para a gravar uma aproximação da medição do peso corporal em um cenário clínico no qual não é possível medir com precisão o peso do corpo - por exemplo, pesar uma criança inquieta, ou estimar o peso de um feto (quando 'sujeito' é um feto e a gravação ocorre no registro da saúde da mãe). Isso não é modelado explicitamente no arquétipo como o modelo de referência da openEHR permite que o atributo de aproximação para qualquer tipo de dados quantitativos. Na execução, por exemplo, uma interface de usuário do aplicativo pode permitir que os clínicos para selecionar uma caixa de seleção devidamente setados junto ao campo de dados de peso, indicando que o peso verificado é uma aproximação, ao invés de reais. 

Usada para gravar a mudança de peso, ou seja, qualquer perda ou ganho de peso. Pode ser modelado por restringir a 'qualquer evento' a um intervalo associado com funções matemáticas de aumentar ou diminuir, conforme o caso.">
			keywords = <"*weight(en)", "*gain(en)", "*loss(en)", "*increase(en)", "*decrease(en)", "*mass(en)", "*estimate(en)", "*actual(en)">
			misuse = <"Não deve ser utilizado para gravar o primeiro peso de um bebê logo após o nascimento, que é designado como o seu 'peso' - use a especialização de seu nascimento arquétipo OBSERVATION.body_weight-birth.
Não deve ser usado para registrar o peso do corpo ajustado por exemplo, um cálculo do peso de corpo inteiro de uma pessoa com amputação de membros, com base em medições de outro corpo e um algoritmo -OBSERVATION.body_weight-adjusted.
Não deve ser usado para registrar o peso de um objeto ou parte do corpo.">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"Zur Dokumentation des Gewichtes eines Individuums, sowohl exakt als auch ungefähr.">
			use = <"Zur Dokumentation des tatsächlichen Körpergewichts, auch wenn das Individuum einen Körperteil (angeboren oder später amputiert) vermisst. Sofern benötigt, kann dies im Datenelement 'Störfaktoren' dokumentiert werden. Dies ist der Archetyp, der gewöhnlicherweise für eine typische Gewichtsmessung benutzt werden sollte, z.B. bei Selbstmessung durch das Individuum zu Hause, durch einen Kliniker im Krankenhaus, oder einen Fitness-Trainer in einem Fitness-Center.

Der Archetyp kann auch benutzt werden, um eine Schätzung des Körpergewichts zu dokumentieren, wenn es nicht möglich ist, das Gewicht genau zu bestimmen - z.B. bei der Messung des Gewichts eines nicht kooperativen Kindes, oder bei einem ungeborenen Fötus (hier ist das 'Subjekt der Daten' der Fötus und die Dokumentation erfolgt in der Akte der Mutter). Dass es sich um eine Schätzung handelt wird in diesem Archetyp nicht explizit modelliert, da das openEHR Referenzmodell dies direkt für 'Quantity'-Datentypen unterstützt. In einer konkreten klinischen Anwendung könnte die Benutzerschnittstelle es dem Kliniker z.B. über eine Checkbox ermöglichen, zu dokumentieren, dass es sich um eine Schätzung handelt.">
			keywords = <"Gewicht", "Zunahme", "Verlust", "Masse", "Schätzung">
			misuse = <"Nicht zur Dokumentation des ersten Gewichts eines Neugeboren (Geburtsgewicht) - benutzen Sie hierzu den spezialisierten Archetyp OBSERVATION.body_weight-birth.
Nicht zur Dokumentation des angepassten Körpergewichts, z.B. eine Berechnung des vollständigen Körpergewichts bei einer Person mit amputierter Extremität auf Basis der anderen Körperteile und eines Algorithmus - benutzen Sie OBSERVATION.body_weight-adjusted.
Nicht zur Dokumentation eines Objekts oder eines Teils des Körpers.">
			copyright = <"© openEHR Foundation">
		>
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the body weight of an individual - both actual and approximate.">
			use = <"To be used for recording the actual measurement of body weight, including when the individual is missing a body part due to a congenital cause or after surgical removal.   A statement identifying the physical incompleteness of the body can be recorded in the 'Confounding factors' data element, if required. This is the usual archetype to be used for a typical measurement of weight, for example self-measured by the individual at home, a clinician measurement in a clinic/hospital, or a fitness instructor in a gymnasium.  

Can also be used for recording an approximation of body weight measurement in a clinical scenario where it is not possible to measure accurately body weight - for example, weighing an uncooperative child, or estimating the weight of an unborn fetus (where the 'subject of data' is the Fetus and recording occurs within the mother's health record).  This is not modelled explicitly in the archetype as the openEHR Reference model allows the attribute of Approximation for any Quantity data type.  At implementation, for example, an application user interface could allow clinicians to select an appropriately labelled check box adjacent to the Weight data field to indicate that the recorded weight is an approximation, rather than actual.

To be used for recording weight change, that is, either weight loss or weight gain.  This can currently be modelled by constraining the 'any event' to an interval with associated mathematical function of increase or decrease, as appropriate.">
			keywords = <"weight", "gain", "loss", "increase", "decrease", "mass", "estimate", "actual">
			misuse = <"Not to be used to record the first weight of an infant soon after birth which is designated as their 'birth weight' - use the specialisation of this archetype OBSERVATION.body_weight-birth.
Not to be used to record the adjusted body weight eg a calculation of the full body weight of a person with limb amputation, based on other body part measurements and an algorithm - use OBSERVATION.body_weight-adjusted.
Not to be used to record the weight of an object or body part.">
			copyright = <"© openEHR Foundation">
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			purpose = <"Для записи массы тела человека: фактической или приблизительной.">
			use = <"Использовать для записи фактического измерения массы тела, включая случаи отсутсвия части(-ей) тела, врожденное или после хирургического удаления. Отметка о физической неполноте тела может быть зарегистрирована в элементе данных \"стохастическая погрешность\", если требуется. Это - обычный архетип, используемый для типичного измерения веса, например самоизмеренного человеком дома, измерение клинициста в клинике/больнице, или фитнес-инструктором в гимнастическом зале. 

Может также использоваться для записи примерного измерения массы тела в клиническом сценарии, где не возможно взвешивание - например, сопротивляющийся ребёнок, или для оценики веса внутриутробного плода (где 'предметом данных' является плод, и регистрация происходит в пределах записи о состоянии здоровья матери). Это не оформлено явно в архетипе, поскольку модель openEHR позволяет атрибут «приблизительно» для любого типа данных «количество». При работе, например, прикладной пользовательский интерфейс позволяет клиницистам выбирать соответствующую отметку, смежную с полем данных «вес», чтобы указать, что зарегистрированный вес - приблизительный, а не фактический. 

Использовать для записи изменения веса, то есть, потери веса или увеличения веса.
Это может в настоящее время моделироваться, привязывая 'каждый случай' к интервалу со связанной математической функцией увеличения или уменьшения, соответственно.">
			keywords = <"вес", "масса тела", "прибавка", "потеря", "увеличение", "уменьшение", "оценка", "актуально">
			misuse = <"Не использовать для записи первого веса младенца после рождение, которое обозначено как 'вес при рождении' - использовать специализацию этого архетипа OBSERVATION.body_weight-birth. 
Не использовать для записи массы тела человека с протезами / приспособлениями для вычисление полной массы тела человека с ампутацией, основанной на других измерениях и алгоритме  - использовать архетип OBSERVATION.body_weight-adjusted.
Не использовать, чтобы сделать запись веса части тела или объекта.">
			copyright = <"© openEHR Foundation">
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			purpose = <"Om het lichaamsgewicht van een persoon te registreren - zowel exact als geschat gewicht.">
			use = <"Registreren van een actuele meting van het lichaamsgewicht, ook als deze persoon een lichaamsdeel mist, door een geboorteafwijking of na een chirurgische ingreep. Een verklaring over de fysieke inclompleetheid van het lichaam, kan zo nodig opgeslagen worden in het data element 'beïnvloedende factoren'. Dit is het gebruikelijke archetype voor gewichtmetingen, bij voorbeeld thuis gemeten door de persoon zelf, een klinische meting in een kliniek/ziekenhuis, of door een fitness instructeur in een sportschool.

Kan ook gebruikt worden om een geschat lichaamsgewicht te registreren in een klinische setting als het niet mogelijk is om het exacte lichaamsgewicht te meten - bijvoorbeeld, het wegen van een tegenwerkend kind, of een schatting van het gewicht van een ongeboren kind (waar het onderwerp van de gegevens de foetus is en de opslag in het patiënten dossier van de moeder plaatsvindt). Dit is niet expliciet gemodelleerd in het archetype, omdat het openEHR Referentie model een schatting in ieder kwantitatief data type toestaat. Bij de uitvoering, bijvoorbeeld, zou een applicatie gebruikersinterface, clinici een adequaat geëtiketteerd selectievakje kunnen aanbieden, naast de gegevens over het gewicht, waarin door selecteren aangegeven kan worden dat het opgenomen gewicht een schatting is, in plaats van het werkelijke gewicht.

Dient te worden gebruikt om gewichtsverandering op te slaan, zowel gewichtsverlies als gewichtstoename.  Dit kan gemodelleerd worden door 'any event' - elke gebeurtenis - in voorkomende gevallen, te beperken tot een interval met met bijbehorende rekenkundige functie van stijging of daling.">
			keywords = <"gewicht", "stijging", "verlies", "toename", "daling", "massa", "schatting", "werkelijk", "afname">
			misuse = <"Dient niet te worden gebruikt voor het registreren van het eerste gewicht van een kind, na geboorte, welke wordt aangewezen als geboortegewicht. Gebruik hiervoor de specialisatie van dit archetype, OBSERVATION.body_weight-birth (OBSERVATION.lichaamsgewicht-geboorte.
Dient niet te worden gebruikt voor het registreren van het aangepaste lichaamsgewicht, bijvoorbeeld een berekening van het volledige lichaamsgewicht van een persoon met een amputatie van ledematen, gebaseerd op metingen van lichaamsdelen en een algoritme - gebruik hiervoor OBSERVATION.body_weight-adjusted. (OBSERVATION.lichaamsgewicht-aangepast).
Dient niet te worden gebruikt voor het vastleggen van het gewicht van een object of lichaamsdeel.">
			copyright = <"© openEHR Foundation">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			purpose = <"برای ثبت وزن بدن فرد ، بطور واقعی یا تقریبی ، بکار می رود">
			use = <"برای ثبت اندازه گیری واقعی وزن بکار می رود، و شامل زمانی که فرد مادرزادی عضوی را ندارد یا بعد از جراحی عضوی را ازدست می دهد، نیز می‌‌شود. عبارتی که نواقص فیزیکی بدن را مشخص می کند در بخش داده های \"فاکتورهای جانبی\" درصورت نیاز ثبت می شود.این الگوساز بطور معمولی برای اندازه گیری واقعی وزن استفاده می شود برای مثال اندازه گیری وزن توسط خود فرد در منزل ، اندازه گیری بالینی در مطب یا بیمارستان یا مربی ورزشی در باشگاه
همچنین از این الگو ساز می توان در اندازه گیری تقریبی وزن بدن در یک سناریوی بالینی، که اندازه گیری واقعی عملی نیست، استفاده نمود برای مثال اندازه گیری وزن کودکی که همکاری نمی کند یا تخمین وزن جنین بدنیا نیامده (که آنجا \"موضوع داده\" جنین است و اطلاعات در پرونده بهداشتی مادر ثبت می‌شوند). این مورد بطور واضح در الگوساز مدل بندی نشده است ولی مدل مرجع \"اوپن ئی اچ ار\" ویژگی تقریب را برای هر نوع داده کمی اجازه می دهد. در پیاده سازی، برای مثال، یک واسط کاربری نرم افزار می تواند به کاربران اجازه دهد تا با انتخاب گزینه ای [چک باکس] درکنار محل مربوط به وزن با نشانه گذاری مناسب نشان دهند که قد ثبت شده اندازه ای است تقریبی و نه  واقعی
     این الگوساز برای تغییرات وزن ، کاهش یا افزایش آن، استفاده می شود. این الگوساز می‌تواند در حال حاضر با مشروط کردن \"هر رویداد\" به دوره زمانی در نظر گرفته شده در الگو، با عملگرهای ریاضی مرتبط با افزایش یا کاهش، بصورت مناسب مدل بندی شود
 
">
			keywords = <"وزن", "زیاد کردن وزن", "کم کردن وزن", "افزایش", "کاهش", "توده", "تخمین", "واقعی">
			misuse = <"برای ثبت اولین اندازه گیری وزن نوزاد بلافاصله بعد ازتولد به عنوان \"وزن نوزاد هنگام تولد\" استفاده نمی شود، در این موارد پیاده سازی اختصاصی از این الگوساز استفاده شود. ببینید
OBSERVATION.weight-birth
برای ثبت  وزن معادل (تطبیق یافته)، مانند محاسبه کل وزن یک فرد قطع عضوی، بر اساس اندازه گیری های بخشهایی از بدن و یا یک الگوریتم دیگر استفاده نشود. در این موارد از 
OBSERVATION.weight-adjusted
استفاده کنید.
برای ثبت وزن یک شی یا بخشهایی از بدن استفاده نکنید
">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"لتسجيل وزن الجسم للشخص - بما في ذلك الوزن الحقيقي و المُقَدَّر">
			use = <"يستخدم لتسجيل القياس الحقيقي لوزن الجسم, بما في ذلك ما إذا كان الشخص قد فقد جزءا من جسمه لسبب خَلقي وراثي, أو بعد استئصال جراحي.
بيان يقوم بتعريف مدى عدم الاكتمال البدني, و يمكن تسجيله تحت عنصر البيانات (العوامل المربكة), حسب الحاجة.
و هذا هو النموذج المعتاد الذي يستخدم للتسجيل النمطي للوزن, مثلا إذا قاسه الشخص لنفسه في المنزل, أو إذا قام الطبيب السريري بالقياس في العيادة/المستشفى, أو المُدرِّب البدني في القاعة الرياضية.

يمكن أيضا أن يستخدم لتسجيل تقدير قياس وزن الجسم في سيناريو سريري حيث لا يمكن قياس وزن الجسم بشكل دقيق - مثلا, قياس وزن طفل غير متعاون, أو تقدير وزن جنين قبل الولادة - حيث يكون الهدف هو قياس وزن الجنين في حين يتم تسجيل ذلك في السجل الطبي للأم

و لا يتم وضع هذا في نموذج صريح حيث يسمح النموذج المرجعي لـ
openEHR
لصفة التقريب لأي نوع كمي من البيانات. 
و عند تشغيل هذا النموذج, مثلا شاشة لبرنامج كمبيوتر فإنها تسمح للطبيب السريري أن يختار زراّ مناسبا ملاصقا لبيانات الوزن تشير إلى أن هذا القياس هو تقدير و ليس حقيقيا.">
			keywords = <"الوزن", "الزيادة/الكسب", "الفاقد", "الزيادة", "النقصان", "الكتلة", "التقدير", "الحقيقي">
			misuse = <"لا يستخدم لتسجيل القياس الأول لوزن حديث الولادة بمجرد ولادته و الذي يسمى بالوزن عند الولادة/ الوضع - و استخدم بدلا من ذلك تخصيص النموذج الذي يسمى ملاحظة.وزن الجسم - الولادة/ الوضع.

لا يستخدم لتسجيل وزن الجسم المُصحَّح مثل قياس الوزن الكلي للجسم لشخص يعاني من بتر في أحد الأطراف, بناءا على قياسات أخرى من الجسم باستخدام خُوارزمية - استخدم بدلا من ذلك نموذج ملاحظة.وزن الجسم المُصحَّح.

لا يستخدم لتسجيل وزن شيئ أو جزء من أجزاء الجسم.">
			copyright = <"© openEHR Foundation">
		>
		["es"] = <
			language = <[ISO_639-1::es]>
			purpose = <"Registro del peso corporal de un individuo ya sea exacto o aproximado.">
			use = <"Se usará para el registro de la medición real del peso del cuerpo, incluso cuando falte una parte del cuerpo debido a una anomalía congénita o después de una extirpación quirúrgica. Este hecho se registra de forma complementaria en un campo asignado ex-profeso. También se puede utilizar para el registro del peso aproximado en un escenario clínico en el que no es posible medir con precisión el peso corporal - por ejemplo, el peso de un niño no coopera, o la estimación del peso de un feto (donde el sujeto de los datos es el feto y la grabación se produce dentro de registros de salud de la madre). En la aplicación, por ejemplo, una interfaz de usuario podría permitir a los médicos seleccionar una casilla de verificación debidamente etiquetada junto al campo \"peso\" para indicar que el peso registrado es una aproximación.

Se usará para reflejar el cambio de registro de peso, es decir, aumento o pérdida de peso. Esto se puede modelar mediante la limitación de \"cualquier evento\" a un intervalo asociado a una función matemática de incremento o decremento, según corresponda.">
			keywords = <"peso", "ganancia", "pérdida", "incremento", "decremento", "masa", "estimado", "real">
			misuse = <"No debe ser usado para grabar el primer registro de peso de un recién nacido (\"el peso al nacer\") que cuenta con su propio arquetipo.
No debe ser usado para registrar el peso corporal ajustado mediante algoritmos.
No debe ser usado para registrar el peso de un objeto o parte del cuerpo.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"Published">
	other_contributors = <"Marja Buur-Krom, Medisch Centrum Alkmaar, Netherlands", "Rong Chen, Cambio Healthcare Systems, Sweden", "Hans Demski, Helmholtz Zentrum München, Germany", "Paul Donaldson, Nursing Informatics Australia, Australia", "Sebastian Garde, Ocean Informatics, Germany", "Heather Grain, Llewelyn Grain Informatics, Australia", "Anne Harbison, CPCER, Australia", "Sam Heard, Ocean Informatics, Australia", "Andrew James, University of Toronto, Canada", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Rikard Lovstrom, Swedish Medical Association, Sweden", "Ian McNicoll, Ocean Informatics, United Kingdom", "Jeroen Meintjens, Medisch Centrum Alkmaar, Netherlands", "Soon Ghee Yap, Singapore Health Services Pte Ltd, Singapore">
	other_details = <
		["MD5-CAM-1.0.1"] = <"98C6C1BFC287FD7414477A390E9E8926">
	>

definition
	OBSERVATION[at0000] matches {	-- Масса тела
		data matches {
			HISTORY[at0002] matches {	-- История
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0003] occurrences matches {0..*} matches {	-- Любое событие
						data matches {
							ITEM_TREE[at0001] matches {	-- Простой
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0004] matches {	-- Вес
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::124]>
												list = <
													["1"] = <
														units = <"kg">
														magnitude = <|0.0..1000.0|>
													>
													["2"] = <
														units = <"lb">
														magnitude = <|0.0..2000.0|>
													>
												>
											>
										}
									}
									ELEMENT[at0024] occurrences matches {0..1} matches {	-- Комментарии
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
						state matches {
							ITEM_TREE[at0008] matches {	-- state structure
								items cardinality matches {0..*; ordered} matches {
									ELEMENT[at0009] occurrences matches {0..1} matches {	-- Наличие и характер одежды
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0011, 	-- В лёгкой одежде или раздевшись до белья
													at0013, 	-- Обнажен
													at0010, 	-- В одежде без обуви
													at0017; 	-- В памперсе
													at0011]	-- assumed value
												}
											}
										}
									}
									ELEMENT[at0025] occurrences matches {0..*} matches {	-- Стохастическая погрешность
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0015] matches {	-- protocol structure
				items cardinality matches {0..*; ordered} matches {
					allow_archetype CLUSTER[at0020] occurrences matches {0..1} matches {	-- Устройство
						include
							archetype_id/value matches {/openEHR-EHR-CLUSTER\.device(-[a-zA-Z0-9_]+)*\.v1/}
					}
				}
			}
		}
	}


ontology
	term_definitions = <
		["nl"] = <
			items = <
				["at0000"] = <
					text = <"Lichaamsgewicht">
					description = <"Meting van het lichaamsgewicht van een individu.">
				>
				["at0001"] = <
					text = <"*Simple(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"Elke gebeurtenis">
					description = <"Elke gebeurtenis.">
				>
				["at0004"] = <
					text = <"Gewicht">
					description = <"Het gewicht van het individu.">
				>
				["at0008"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0009"] = <
					text = <"Hoeveelheid kleding">
					description = <"Beschrijving van de hoeveelheid kleding van de persoon, op het moment van wegen.">
				>
				["at0010"] = <
					text = <"Volledig gekleed, inclusief schoenen">
					description = <"Kleren die een significante bijdrage hebben aan het gewicht, inclusief schoenen.">
				>
				["at0011"] = <
					text = <"Lichte kleding/ondergoed">
					description = <"Kleding die niet significant het gewicht beÏnvloedt.">
				>
				["at0013"] = <
					text = <"Naakt">
					description = <"Zonder kleding.">
				>
				["at0015"] = <
					text = <"*protocol structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0017"] = <
					text = <"Luier">
					description = <"Individu draagt alleen een luier - zou significant aan het gewicht kunnen bijdragen.">
				>
				["at0020"] = <
					text = <"Apparaat">
					description = <"Details over het weeginstrument.">
				>
				["at0024"] = <
					text = <"Opmerking">
					description = <"Opmerking over de gewichts meting.">
				>
				["at0025"] = <
					text = <"BeÏnvloedende factoren">
					description = <"Registreer eventuele problemen of factoren die van invloed kunnen zijn op de meting van het lichaamsgewicht bijvoorbeeld timing in de menstruele cyclus, timing van de recente stoelgang of het noteren van een amputatie.">
				>
			>
		>
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Body weight">
					description = <"Measurement of the body weight of an individual.">
				>
				["at0001"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"Any event">
					description = <"Any event.">
				>
				["at0004"] = <
					text = <"Weight">
					description = <"The weight of the individual.">
				>
				["at0008"] = <
					text = <"state structure">
					description = <"@ internal @">
				>
				["at0009"] = <
					text = <"State of Dress">
					description = <"Description of the state of dress of the person at the time of weighing.">
				>
				["at0010"] = <
					text = <"Fully clothed, including shoes">
					description = <"Clothing which may add significantly to weight, including shoes.">
				>
				["at0011"] = <
					text = <"Lightly clothed/underwear">
					description = <"Clothing which will not add to weight significantly.">
				>
				["at0013"] = <
					text = <"Naked">
					description = <"Without any clothes.">
				>
				["at0015"] = <
					text = <"protocol structure">
					description = <"@ internal @">
				>
				["at0017"] = <
					text = <"Nappy/diaper">
					description = <"Wearing only a nappy - can add significant weight.">
				>
				["at0020"] = <
					text = <"Device">
					description = <"Details about the weighing device.">
				>
				["at0024"] = <
					text = <"Comment">
					description = <"Comment about the measurement of weight.">
				>
				["at0025"] = <
					text = <"Confounding Factors">
					description = <"Record any issues or factors that may impact on the measurement of body weight eg timing in menstrual cycle, timing of recent bowel motion or noting of amputation.">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"Körpergewicht">
					description = <"Messung des Körpergewichts eines Individuums.">
				>
				["at0001"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"History">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"*Any event(en)">
					description = <"*Any event(en)">
				>
				["at0004"] = <
					text = <"Gewicht">
					description = <"Das Gewicht eines Individuums.">
				>
				["at0008"] = <
					text = <"State structure">
					description = <"@ internal @">
				>
				["at0009"] = <
					text = <"Bekleidung">
					description = <"Beschreibung der Bekleidung zum Zeitpunkt der Messung.">
				>
				["at0010"] = <
					text = <"Voll bekleidet, mit Schuhen">
					description = <"Bekleidung, die signifikant zum Gewicht beiträgt, mit Schuhen.">
				>
				["at0011"] = <
					text = <"Leicht bekleidet / Unterwäsche">
					description = <"Bekleidung, die nicht signifikant zum Gewicht beiträgt.">
				>
				["at0013"] = <
					text = <"Unbekleidet">
					description = <"Ohne Kleidung.">
				>
				["at0015"] = <
					text = <"Protocol structure">
					description = <"@ internal @">
				>
				["at0017"] = <
					text = <"Windel">
					description = <"Trägt Windel; kann signifikant zum Gewicht beitragen.">
				>
				["at0020"] = <
					text = <"Gerät">
					description = <"Details über die benutzte Waage.">
				>
				["at0024"] = <
					text = <"Kommentar">
					description = <"Kommentar über die Messung des Gewichts.">
				>
				["at0025"] = <
					text = <"Störfaktoren">
					description = <"Zur Dokumentation von Faktoren, die einen Einfluss auf die Messung des Körpergewichts haben können, z.B. Zeitpunkt in der Menstruationsperiode, Zeitpunkt des letzten Stuhlgangs, durchgeführte Amputationen.">
				>
			>
		>
		["pt-br"] = <
			items = <
				["at0000"] = <
					text = <"Peso corporal">
					description = <"A medição do peso corporal de um indivíduo.">
				>
				["at0001"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"Qualquer evento">
					description = <"Qualquer evento.">
				>
				["at0004"] = <
					text = <"Peso">
					description = <"O peso do indivíduo.">
				>
				["at0008"] = <
					text = <"state structure">
					description = <"@ internal @">
				>
				["at0009"] = <
					text = <"Vestuário">
					description = <"Descrição do vestuário da pessoa na hora da pesagem.">
				>
				["at0010"] = <
					text = <"Totalmente vestida, incluindo sapatos">
					description = <"Roupas que podem aumentar significativamente o peso, incluindo sapatos.">
				>
				["at0011"] = <
					text = <"Levemente vestido / roupa íntimas">
					description = <"Roupas que não irão acrescentar ao peso de forma significativa.">
				>
				["at0013"] = <
					text = <"Despido">
					description = <"Sem nenhuma roupa.">
				>
				["at0015"] = <
					text = <"protocol structure">
					description = <"@ internal @">
				>
				["at0017"] = <
					text = <"Fralda">
					description = <"Vestindo apenas uma fralda - pode adicionar peso significativo.">
				>
				["at0020"] = <
					text = <"Dispositivo">
					description = <"Detalhes sobre o dispositivo de pesagem.">
				>
				["at0024"] = <
					text = <"Comentário">
					description = <"Comentário sobre a medição do peso.">
				>
				["at0025"] = <
					text = <"Fatores de erro">
					description = <"Registrar quaisquer problemas ou fatores que possam ter impacto sobre a medição de peso corporal, por exemplo, no momento do ciclo menstrual, o ciclo intestinal ou anotando amputação.">
				>
			>
		>
		["ru"] = <
			items = <
				["at0000"] = <
					text = <"Масса тела">
					description = <"Измерение актуальной массы тела человека.">
				>
				["at0001"] = <
					text = <"Простой">
					description = <"Bнутренний элемент.">
				>
				["at0002"] = <
					text = <"История">
					description = <"Bнутренний элемент.">
				>
				["at0003"] = <
					text = <"Любое событие">
					description = <"Любое событие.">
				>
				["at0004"] = <
					text = <"Вес">
					description = <"Актуальный вес человека.">
				>
				["at0008"] = <
					text = <"state structure">
					description = <"@ internal @">
				>
				["at0009"] = <
					text = <"Наличие и характер одежды">
					description = <"Описание наличия и характера одежды пациента во время взвешивания.">
				>
				["at0010"] = <
					text = <"В одежде без обуви">
					description = <"Одежда может добавить значительный вес.">
				>
				["at0011"] = <
					text = <"В лёгкой одежде или раздевшись до белья">
					description = <"Одежда, не добавляющая значительный вес.">
				>
				["at0013"] = <
					text = <"Обнажен">
					description = <"Без какой-либо одежды и белья.">
				>
				["at0015"] = <
					text = <"protocol structure">
					description = <"@ internal @">
				>
				["at0017"] = <
					text = <"В памперсе">
					description = <"Одет(а) только в памперс - может добавить значительный вес.">
				>
				["at0020"] = <
					text = <"Устройство">
					description = <"Весы (устройство, на котором производилось взвешивание): информация.">
				>
				["at0024"] = <
					text = <"Комментарии">
					description = <"Комментарии к взвешиванию.">
				>
				["at0025"] = <
					text = <"Стохастическая погрешность">
					description = <"Фиксация любых фактов, могущих повлиять на результат взвешивания: фаза менструального цикла, давность опорожнения кишечника, сведения об ампутации и др.">
				>
			>
		>
		["fa"] = <
			items = <
				["at0000"] = <
					text = <"وزن بدن">
					description = <"اندازه گیری وزن بدن فرد">
				>
				["at0001"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"هر رویداد">
					description = <"هر رویداد">
				>
				["at0004"] = <
					text = <"وزن">
					description = <"وزن فرد">
				>
				["at0008"] = <
					text = <"state structure">
					description = <"@ internal @">
				>
				["at0009"] = <
					text = <"میزان لباس">
					description = <"توصیف میزان لباس فرد در زمان اندازه گیری وزن ">
				>
				["at0010"] = <
					text = <"کاملا لباس پوشیده ، از جمله کفش">
					description = <"لباسی که ممکن است بطور قابل توجهی به وزن بیافزاید شامل کفش ها">
				>
				["at0011"] = <
					text = <"لباس سبک یا لباس زیر">
					description = <"لباسی که بطور قابل توجهی وزن را افزایش ندهد">
				>
				["at0013"] = <
					text = <"لخت">
					description = <"بدون هر گونه لباس">
				>
				["at0015"] = <
					text = <"protocol structure">
					description = <"@ internal @">
				>
				["at0017"] = <
					text = <"کهنه بچه یا پوشک">
					description = <"پوشیدن فقط یک پوشک که می تواند وزن را بطور قابل توجهی افزایش دهد">
				>
				["at0020"] = <
					text = <"تجهیز">
					description = <"توصیف تجهیز استفاده شده برای اندازه گیری وزن">
				>
				["at0024"] = <
					text = <"نظر">
					description = <"نظر در مورد اندازه گیری وزن ">
				>
				["at0025"] = <
					text = <"فاکتورهای جانبی">
					description = <"ثبت هر گونه مساله یا فاکتوری که ممکن است روی اندازه گیری وزن در زمان اندازه گیری تاثیر داشته باشه به عنوان مثال در زمان عادت ماهیانه ،دفع مدفوع، یا ثبت قطع عضو">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"وزن الجسم">
					description = <"قياس وزن الجسم للشخص">
				>
				["at0001"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"إحدى الوقائع">
					description = <"إحدى الوقائع">
				>
				["at0004"] = <
					text = <"الوزن">
					description = <"وزن الشخص">
				>
				["at0008"] = <
					text = <"state structure">
					description = <"@ internal @">
				>
				["at0009"] = <
					text = <"حالة الملبس">
					description = <"وصف حالة الملبس الذي يرتديه الشخص في وقت قياس الوزن.">
				>
				["at0010"] = <
					text = <"ملابس كاملة, بما في ذلك الأحذية">
					description = <"الشخص يرتدي ملابس قد تزيد الوزن بشكل مؤثر, بما في ذلك الأحذية.">
				>
				["at0011"] = <
					text = <"ملابس خفيفة/ ملابس داخلية">
					description = <"ملابس لا تزيد الوزن بشكل مؤثر">
				>
				["at0013"] = <
					text = <"مُعَرَّى">
					description = <"لا يرتدي أي ملابس">
				>
				["at0015"] = <
					text = <"protocol structure">
					description = <"@ internal @">
				>
				["at0017"] = <
					text = <"حفاظة">
					description = <"الشخص يرتدي حفاظة فقط - و قد يزيد ذلك من الوزن بشكل مؤثر">
				>
				["at0020"] = <
					text = <"الجهيزة">
					description = <"تفاصيل حول الجهيزة المستخدمة في القياس">
				>
				["at0024"] = <
					text = <"التعليق">
					description = <"تعليق حول قياس الوزن">
				>
				["at0025"] = <
					text = <"العوامل المربكة">
					description = <"لتسجيل أي قضايا أو عوامل قد تؤثر في قياس وزن الجسم, مثل الوقت من الدورة الشهرية, آخر مرة لإفراغ الأمعاء أو ملاحظة وجود بتر في أحد الأعضاء">
				>
			>
		>
		["es"] = <
			items = <
				["at0000"] = <
					text = <"Peso corporal">
					description = <"Medición del peso corporal de un individuo.">
				>
				["at0001"] = <
					text = <"*Simple(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"Cualquier evento.">
					description = <"Cualquier evento.">
				>
				["at0004"] = <
					text = <"Peso">
					description = <"Peso del individuo.">
				>
				["at0008"] = <
					text = <"*state structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0009"] = <
					text = <"Indumentaria">
					description = <"Descripción de la indumentaria del sujeto en el momento de la medición.">
				>
				["at0010"] = <
					text = <"Totalmente vestido incluyendo calzado">
					description = <"La indumentaria, incluyendo calzado, puede incrementar el peso de forma significativa.">
				>
				["at0011"] = <
					text = <"Indumentaria ligera/Ropa interior">
					description = <"La indumentaria no genera un incremento significativo del peso.">
				>
				["at0013"] = <
					text = <"Desnudo">
					description = <"Sin ropa.">
				>
				["at0015"] = <
					text = <"*protocol structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0017"] = <
					text = <"Pañales">
					description = <"Únicamente con un pañal. Puede incrementar el peso de forma significativa.">
				>
				["at0020"] = <
					text = <"Dispositivo">
					description = <"Detalles acerca del dispositivo de pesada.">
				>
				["at0024"] = <
					text = <"Observaciones">
					description = <"Observaciones acerca de la medición del peso.">
				>
				["at0025"] = <
					text = <"Factores de alteración">
					description = <"Registrar cualquier consideración que pueda influir en la medida del peso ej: amputaciones, momento del ciclo menstrual, etc. (en)">
				>
			>
		>
	>

```

Height (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.height.v1

concept
	[at0000]	-- Height/Length
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Jasmin Buck, Sebastian Garde">
				["organisation"] = <"University of Heidelberg, Ocean Informatics">
			>
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			author = <
				["name"] = <"Dr. Leonardo Der Jachadurian">
				["organisation"] = <"Bitios.com">
			>
			accreditation = <"Medical Doctor (Internal Medicine Specialist)">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			author = <
				["name"] = <"Shahla Foozonkhah">
				["organisation"] = <"Ocean Informatics">
			>
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			author = <
				["name"] = <"Marja Buur">
				["organisation"] = <"Medisch Centrum Alkmaar">
				["email"] = <"m.buur-krom@mca.nl">
			>
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			author = <
				["name"] = <"Marco Borges">
				["organisation"] = <"P2D">
				["email"] = <"marco.borges@p2d.com.br">
			>
			accreditation = <"P2D Health Advisor Council">
		>
	>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"2006-03-09">
	>
	details = <
		["nl"] = <
			language = <[ISO_639-1::nl]>
			purpose = <"Registreren van de lengte van het lichaam van hoofdkruin tot voetzool van een individu - zowel werkelijke als geschatte lengte en zowel in staande als liggende positie.">
			use = <"Te gebruiken voor de registratie van de werkelijke lengte/hoogte van een individu op elk moment in de tijd. Een verklaring over fysieke onvolledigheid van het lichaam kan worden opgenomen in het protocol element ‘ beïnvloedende factoren’, indien nodig. Dit is het gebruikelijke archetype voor een typische meting van de hoogte of lengte, onafhankelijk van de klinische setting. 
Kan ook worden gebruikt voor het opnemen van een schatting van de lengte/hoogte meting in een klinisch scenario, waarin het niet mogelijk is om een nauwkeurige lengte te meten - bijvoorbeeld het meten van een onwillig kind. 
Dit is niet expliciet gemodelleerd in het archetype, omdat het openEHR Referentie model een schatting in ieder kwantitatief data type toestaat. Bij de uitvoering, bijvoorbeeld, zou een applicatie gebruikersinterface, een adequaat geëtiketteerd selectievakje kunnen aanbieden aan clinici, naast de gegevens over het gewicht, waarin door selecteren aangegeven kan worden dat het opgenomen gewicht een schatting is, in plaats van het werkelijke gewicht.

In het engelse taaldomein wordt er verschil gemaakt tussen hoogte (height) en lengte (length), waarbij hoogte staande gemeten wordt en lengte liggend.
In dat geval zijn lengte metingen aanbevolen voor kinderen onder de leeftijd van 2 jaar en personen die niet kunnen staan; hoogte metingen voor alle anderen. 
Idealiter wordt de hoogte(NL: lengte) gemeten, staand op beide voeten met het gewicht gelijkmatig verdeeld, hielen tegen elkaar en beide billen en hakken in contact met een verticale achterkant; lichaamslengte wordt gemeten in een volledig uitgespreide rugligging met het bekken plat, benen gestrekt en voeten gebogen. 
Wordt gebruikt voor het registreren van groei en verlies van lengte. Dit kan, in voorkomend geval, momenteel worden gemodelleerd, door het beperken van een 'any event', tot een interval in een template met bijbehorende rekenkundige functie van de groei of krimp.">
			keywords = <"krimp", "groeien", "verlies", "lengte", "hoogte">
			misuse = <"Niet te gebruiken ter registratie van de eerste lengte van een kind, spoedig na de geboorte, welke gekenmerkd wordt als de geboortelengte - gebruik hiervoor de specialisatie van dit archetype - zie OBSERVATION.height-birth.(OBSERVATION.lengte-geboorte).">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"Zur Dokumentation der Körpergröße in einer gestreckten Position, von Scheitel bis Sohle. Dies kann sowohl genau als auch ungefähr erfolgen, und entweder in einer stehenden oder liegenden Position.">
			use = <"Wird verwendet um die tatsächliche Körpegröße/-länge eines Individuums zu dokumentieren. Eine Aussage über die physische Unvollständigkeit des Körpers kann in den 'Einflussfaktoren' des Protokoll Elements dokumentiert werden. Dies ist der gewöhnliche Archetyp zur Dokumentation einer typischen Messung von Körpergröße/-länge, unabhängig von der klinischen Situation.
Der Archetyp kann auch verwendet werden, um eine geschätze Größe/Länge zu dokumentatieren, wenn es nicht möglich ist, eine genaue Messung durchzuführen, z.B. bei der Messung bei einem unkooperativen Kind. Dies ist nicht explizit in dem Archetyp modelliert, da das openEHR Referenzmodell für jeden 'Quantity' Datentyp automatisch das Attribut 'Approximation' zur Verfügung stellt. Zum Zeitpunkt der Implementiertung könnte eine Benutzerschnittstelle es den Klinikern daher ermöglichen, z.B. ein entsprechendes Kontrollkästchen zu aktivieren.
Im allgemeinen werden Längenmessungen für Kinder bis zwei Jahren empfohlen, sowie für Individuen, die nicht stehen können; Größenmessungen für alle anderen. Idealerweise wird die Größe auf beiden Beinen stehend gemessen, mit dem Gewicht gleichmäßig verteilt, den Hacken zusammen und beiden Gesäßbacken und Hacken in Kontakt mit einem senkrechten Brett. Körperlänge wird in einer voll ausgestreckten, liegenden Position gemessen; hierbei wird das Becken flach gehalten, die Beine ausgestreckt und die Füße gebeugt.
Der Archetyp wird auch benutzt, um eine Zunahme/Abnahme der Körpergröße/-länge zu dokumentieren. Dies kann z.B. in einem Template modelliert werden, indem das 'Any event' auf ein Interval eingeschränkt wird, mit der zugehörigen mathematischen Funktion 'increase' or 'decrease'.">
			keywords = <"Größe", "Länge", "Wachstum", "Schrumpfung">
			misuse = <"Nicht zur Dokumentation der ersten Länge eines Neugeboren (Geburtslänge) - hier sollte der spezialisierte Archetyp OBSERVATION.height-birth verwendet werden.
Nicht zur Dokumentation der angepassten Größe oder Körperlänge - z.B. der geschätzten vollen Größe einer Person mit Kontraktur der Extremitäten, basierend auf der Messung anderer Körperteile und/oder einem Algorithmus - hier sollte der spezialisierte Archetyp OBSERVATION.height-adjusted verwendet werden.
Nicht zur Dokumentation von Wachstumsgeschwindigkeit.
Nicht zur Dokumentation der Länge eines Objekts oder spezifischen Körperteils.">
			copyright = <"© openEHR Foundation">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			purpose = <"Para registar o comprimento do corpo de um indivíduo, medindo da coroa da cabeça a sola do pé.
A medida pode ser tanto real como aproximada, quer seja com a posição do indivíduo de pé ou em decúbito dorsal.">
			use = <"Usada para gravar a altura real ou comprimento do corpo de um indivíduo a qualquer momento.
A indicação da imperfeição física do corpo pode ser gravado no elemento 'protocolo fatores de confusão', se necessário.
Este é o arquétipo de uso habitual para a medição típica de altura ou comprimento do corpo, independente da situação clínica. 
Também pode ser usado para a gravação de uma altura aproximada ou de medição do comprimento do corpo em um cenário clínico no qual não é possível medir uma altura ou comprimento exato - por exemplo, a medição de uma criança que não coopera. Isso não é modelada explicitamente no arquétipo como o modelo de referência openEHR permite que o atributo de aproximação para qualquer tipo de dados quantitativos. Na execução, por exemplo, uma interface de usuário do aplicativo pode permitir que os clínicos para selecionar uma caixa de seleção devidamente setados junto ao campo de dados de altura para indicar que a altura registrada é uma aproximação, ao invés de reais. 
Em geral, as medidas de comprimento são recomendados para crianças menores de dois anos de idade e indivíduos que não podem ficar, as medições de altura para todos os outros. 
Idealmente, a altura é medida em pé sobre dois pés com peso distribuído uniformemente, os calcanhares unidos e as duas nádegas e calcanhares em contato com uma placa vertical para trás; comprimento do corpo é medido em uma posição totalmente estendida, supino com a pelve plana, pernas estendidas e os pés flexionados. 
Use para registar um crescimento e perda de altura. Isso pode ser modelado por restringir a 'qualquer evento' a um intervalo em um modelo associado com a função matemática de aumentar ou diminuir, conforme o caso.">
			keywords = <"encolhimento", "crescimento", "diminuição", "diminuição da altura", "altura", "comprimento", "crescimento">
			misuse = <"Não deve ser utilizado para gravar o primeiro comprimento de um bebê, logo após o nascimento. Para isso é designado o \"comprimento de nascimento\" - use a especialização desse arquétipo - ver OBSERVATION.height-birth.
Não deve ser utilizado para registrar a altura ajustada ou comprimento do corpo por exemplo, um cálculo da altura estimada completo de uma pessoa com contraturas dos membros, com base em medições outro corpo e / ou um algoritmo - use OBSERVATION.height-adjusted.
Não deve ser usado para registrar a velocidade de crescimento.
Não deve ser utilizado para gravar o tamanho de um objeto ou parte específica do corpo.">
			copyright = <"© openEHR Foundation">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			purpose = <"برای ثبت طول بدن از نوک سر تا کف پای فرد- بطور واقعی و تقریبی و در حالتهای ایستاده یا خوابیده ">
			use = <"برای ثبت قد یا طول واقعی یک فرد در هر نقطه از زمان بکار برده می شود.عبارتی  که نواقص فیزیکی بدن را مشخص می کند  می تواند درصورت نیاز در بخش پروتکل \" فاکتورهای جانبی \"ثبت شود. ازاین الگو ساز می توان در اندازه گیری های معمول قد یا طول بدن مستقل از وضع بالینی استفاده نمود. 
از این الگو ساز همچنین می توان برای ثبت تقریبی اندازه گیری قد یا طول بدن در سناریوهای بالینی استفاده نمود که امکان اندازه گیری دقیق قد یا طول وجود ندارد، به عنوان مثال اندازه گیری قد یا طول کودکی که همکاری نمی کند. این مورد بطور واضح در الگوساز مدل بندی نشده است ولی مدل مرجع \"اوپن ئی اچ ار\" ویژگی تقریب را برای هر نوع داده کمی اجازه می دهد. در پیاده سازی، برای مثال، یک واسط کاربری نرم افزار می تواند به کاربران اجازه دهد تا با انتخاب گزینه ای [چک باکس] درکنار محل مربوط به قد و با نشانه گذاری مناسب نشان دهند که قد ثبت شده اندازه ای است تقریبی و نه  واقعی.
بطور عمومی اندازه گیری طول بدن برای کودکان زبر 2 سال و بزرگسالانی که نمی توانند بایستند  و انداز گیری قد برای سایر افراد توصیه می شود.
بطور ایده آل قد بصورت ایستاده بر هر دو پا، پاشنه ها کنار هم ، باسن و پاشنه ها در راستای خط عمودی پشت  با توزیع وزن مساوی اندازه گیری می شود، طول بدن در حالت کاملا کشیده و طاقباز با لگن صاف، ساق های کشیده و پاهای جمع شده از مچ اندازه گیری می شود.
این الگوساز برای ثبت رشد و افت قد استفاده می شود. در حال حاضر با مشروط کردن \"هر رویداد\" به دوره زمانی در نظر گرفته شده در الگو با عملگرهای ریاضی مرتبط با افزایش یا کاهش بصورت مناسب مدل بندی می شود
 
">
			keywords = <"انقباض", "افزایش", "کاهش", "افت قد", "قد", "طول", "رشد">
			misuse = <"برای ثبت اولین اندازه گیری نوزاد بلافاصله بعد ازتولد به عنوان \"طول نوزاد هنگام تولد\" استفاده نمی شود، در این موارد از حالت تخصصی الگوساز استفاده شود. ببینید
OBSERVATION.height-birth
برای ثبت قد یا طول بدن معادل (تطبیق یافته)، مانند محاسبه تخمینی کل قد یک فرد با اندام منقبض، بر اساس اندازه گیری های بخشهایی از بدن و یا یک الگوریتم دیگر استفاده نشود. در این موارد از 
OBSERVATION.height-adjusted
استفاده کنید.
برای ثبت رشد قد استفاده نکنید
برای ثبت طول یک شی یا بخشهایی از بدن استفاده نکنید
">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"لتسجيل طول الجسم من تاج الرأس إلى أخمص القدم للفرد - يشتمل على كل من القياس التقديري و الحقيقي, سواء أكان الفرد واقفا أو مستلقيا.">
			use = <"يستخدم لتسجيل الارتفاع أو الطول الحقيقي لجسم الفرد عند أي نقطة من الزمن. و هو بيان لتعريف عدم الاكتمال الجسدي للجسم, و يمكن تسجيله في عنصر العوامل المربكة, إذا لزم. 
هذا هو النموذج المعتاد ليستخدم في القياس النمطي لارتفاع أو طول الجسم, مستقلا عن الإطار السريري.

يمكن استخدامه أيضا في تسجيل قياس تقريبي لارتفاع أو طول الجسم في سيناريو سريري لا يمكن فيه قياس الطول أو الارتفاع بشكل حقيقي – مثلا, قياس طفل غير متعاون. 

و ليس هذا متمثلا بشكل صريح في هذا النموذج حيث إن النموذج المرجعي للـ open EHR  
يسمح بوجود صفة التقريب لأي نوع بيانات كمي.

و عند التنفيذ, مثلا, الشاشة الإلكترونية تسمح للأطباء السريريين أن يختاروا زرا بجوار قياس الطول ليشير إلى أنه قياس تقريبي, و ليس حقيقيا.
و بشكل عام, فإن قياسات الطول يستحسن استخدامها للأطفال أقل من عامين و للأفراد الذين لا يستطيعون الوقوف, أما قياسات الارتفاع فيمكن استخدامها لباقي الحالات.

و الوضع المثالي لقياس الارتفاع يكون بالوقوف على القدمين مع توزيع الوزن بشكل متساوٍ, و وضع الكعبين متجاورين, و كلا الأليتين متلامستين مع لوح ظهري عمودي, و يتم قياس طول الجسم في وضع مستلقٍٍ متمدد بشكل تام مع استواء الحوض, و الأرجل ممتدة و الأقدام مرتخية.

يستخدم لقياس النمو و النقص في الطول. و يمكن حاليا وضعه في نموذج (إحدى الوقائع) بتقييده ليمثل فاصلا في إحدى القوالب مع دالة حسابية مصاحبة لحساب الزيادة أو النقص متى كان ذلك مناسبا.">
			keywords = <"الانكماش", "الزيادة", "النقص", "فقد الارتفاع", "الطول", "الارتفاع", "النمو">
			misuse = <"لا يستخدم لتسجيل أول قياس لطول المولود بعد الولادة بفترة قصيرة, و الذي يشار إليه بالطول عند الولادة - و استخدم بدلا من ذلك النموذج المخصص بعنوان ملاحظة. الطول عند الولادة.
لا يستخدم لتسجيل الطول أو الارتفاع المُصَحَّح مثل الطول الكلي التقديري للفرد الذي يعاني من تقلصات الأطراف, بناء على قياسات أجزاء أخرى من الجسم و / أو لوغاريتم - استخدم بدلا من ذلك نموذج ملاحظة . الطول المصحح. 
لا يستخدم لقياس سرعة النمو.
لا يستخدم لتسجيل طول شيئ ما أو جزء معين من الجسم.">
			copyright = <"© openEHR Foundation">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			purpose = <"Para registrar la longitud corporal desde la coronilla de la cabeza hasta la planta de los pies, en el momento actual y tanto en posición parada como recostada.">
			use = <"Usar para registrar la altura o longitud corporal actuales en cualquier momento. En caso de amputaciones u otra causa de incompletitud corporal puede ser registrado en \"Factores de confusión\", si es requerido. Este es el arquetipo usual para ser usado en una medición típica de altura o longitud corporal, independientemente del contexto clínico.

También puede ser usado para registrar una aproximación de la altura o longitud corporal en un contexto clínico donde no es posible realizar una medición exacta (Ej. en el caso de un niño que no coopera). Esto no es modelado explícitamente en el arquetipo como el modelo de referencia de openEHR permite el atributo de aproximación para cualquier tipo  de dato de Cantidad. En la implementación, por ejemplo, la interfaz con el usuario de una aplicación de software podría permitir a los médicos tildar un cuadro de opción adyacente al campo de datos de Altura, para indicar que el dato registrado es una aproximación, antes que el valor medido exacto.

En general, la medición de la longitud corporal se recomienda para niños menores a los 2 años y para individuos que no pueden permanecer de pie; medir altura para todos los demás casos.

Idealmente, la altura es medida de pie sobre ambos pies con el peso distribuido equitativamente entre ambos, con los talones juntos y ambos glúteos y talones en contacto con una tabla posterior vertical y recta; la longitud corporal se mide en posición recostada completamente extendida, con la pelvis plana, las piernas extendidas y los pies flexionados.

Usar para registrar el crecimiento o la pérdida de altura. Esto puede ser habitualmente modelado restringiendo \"cualquier evento\" a un intervalo en la plantilla, con una función matemática que incrementa o decrementa, según sea apropiado.">
			keywords = <"contracción", "aumentar", "disminuir", "pérdida de altura", "altura", "longitud corporal", "crecimiento", "talla", "estatura">
			misuse = <"No usar para registrar la primer talla de un infante en un momento cercano a su nacimiento, usualmente denominado como \\\"altura al nacer\\\". Para este uso utilizar la especialización de este arquetipo (ver OBSERVATION.height-birth.)

No usar para registrar la altura o la longitud corporal ajustados (Ej. el calculo de la altura total estimada de una persona con contracturas de miembros, basado en las mediciones realizadas en otras partes del cuerpo y/o un algoritmo) Usar para esta situación: OBSERVATION.height-adjusted.

No usar para registrar velocidad de crecimiento.

No usar para registrar la longitud de un objeto o de una parte del cuerpo específica.">
			copyright = <"© openEHR Foundation">
		>
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the length of the body from crown of head to sole of foot of an individual - both actual and approximate, and either in a standing or recumbent position.">
			use = <"To be used for recording the actual height or body length of an individual at any point in time.  A statement identifying the physical incompleteness of the body can be recorded in the 'Confounding factors' protocol element, if required.  This is the usual archetype to be used for a typical measurement of height or body length, independent of the clinical setting.
Can also be used for recording an approximation of height or body length measurement in a clinical scenario where it is not possible to measure an accurate height or length - for example, measuring an uncooperative child.  This is not modelled explicitly in the archetype as the openEHR Reference model allows the attribute of Approximation for any Quantity data type.  At implementation, for example, an application user interface could allow clinicians to select an appropriately labelled check box adjacent to the Height data field to indicate that the recorded height is an approximation, rather than actual.
In general, length measurements are recommended for children under 2 years of age and individuals who cannot stand; height measurements for all others.
Ideally, height is measured standing on both feet with weight distributed evenly, heels together and both buttocks and heels in contact with a vertical back board; body length is measured in a fully extended, supine position with the pelvis flat, legs extended and feet flexed. 
Use to record growth and loss of height.  This can currently be modelled by constraining the 'any event' to an interval in a template with associated mathematical function of increase or decrease, as appropriate.">
			keywords = <"shrinkage", "increase", "decrease", "height loss", "height", "length", "growth">
			misuse = <"Not to be used to record the first length of an infant soon after birth which is designated as their 'birth length' - use the specialisation of this archetype - see OBSERVATION.height-birth.
Not to be used to record the adjusted height or body length eg a calculation of the estimated full height of a person with limb contractures, based on other body part measurements and/or an algorithm - use OBSERVATION.height-adjusted.
Not to be used to record growth velocity.
Not to be used to record the length of an object or specific body part.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Jeroen Meintjen, Medisch Centrum Alkmaar, Netherlands", "Sebastian Garde, Ocean Informatics, Germany", "Heather Leslie, Ocean Informatics, Australia", "Omer Hotomaroglu, Turkey", "Andrew James, University of Toronto, Canada", "Anne Harbison, Australia", "Thilo Schuler, Germany", "Anneke Goossen, Results 4 Care, Netherlands", "Rikard Lovstrom, Swedish Medical Association, Sweden", "Heather Grain, Llewelyn Informatics, Australia", "Hans Demski, Helmholtz Zentrum München, Germany", "Soon Ghee Yap, Singapore Health Services Pte Ltd, Singapore", "Paul Donaldson, Nursing Informatics Australia, Australia", "Rong Chen, Cambio Healthcare Systems, Sweden", "Sundaresan Jagannathan, Scottish NHS, United Kingdom", "Ian McNicoll, Ocean Informatics, United Kingdom", "Marja Buur, Medisch Centrum Alkmaar, Netherlands">
	other_details = <
		["references"] = <"Wilks Z, Bryan S, Mead V and Davies EH. Clinical guideline: Height, measuring a child [Internet]. London, United Kingdom: UCL Institute of Child Health; 2008 Apr 01 [cited 2009 Jul 28 ]. Available from: http://www.ich.ucl.ac.uk/clinical_information/clinical_guidelines/cpg_guideline_00060">
		["MD5-CAM-1.0.1"] = <"D85CD579475783F0738EAFCF4BC9E4B5">
	>

definition
	OBSERVATION[at0000] matches {	-- Height/Length
		data matches {
			HISTORY[at0001] matches {	-- history
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0002] occurrences matches {1..*} matches {	-- Any event
						data matches {
							ITEM_TREE[at0003] matches {	-- Simple
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0004] matches {	-- Height/Length
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::122]>
												list = <
													["1"] = <
														units = <"cm">
														magnitude = <|0.0..1000.0|>
													>
													["2"] = <
														units = <"in">
														magnitude = <|0.0..250.0|>
													>
												>
											>
										}
									}
									ELEMENT[at0018] occurrences matches {0..1} matches {	-- Comment
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
						state matches {
							ITEM_TREE[at0013] matches {	-- Tree
								items cardinality matches {0..*; unordered} matches {
									ELEMENT[at0014] occurrences matches {0..1} matches {	-- Position
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0016, 	-- Standing
													at0020; 	-- Lying
													at0016]	-- assumed value
												}
											}
										}
									}
									ELEMENT[at0019] occurrences matches {0..1} matches {	-- Confounding factors
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0007] matches {	-- List
				items cardinality matches {0..*; ordered} matches {
					allow_archetype CLUSTER[at0011] occurrences matches {0..1} matches {	-- Device
						include
							archetype_id/value matches {/openEHR-EHR-CLUSTER\.device(-[a-zA-Z0-9_]+)*\.v1/}
					}
				}
			}
		}
	}


ontology
	term_definitions = <
		["nl"] = <
			items = <
				["at0000"] = <
					text = <"Lengte">
					description = <"De lichaamslengte wordt gemeten vanaf de kruin van het hoofd tot en met de voetzool. In het engelse taaldomein wordt er verschil gemaakt tussen hoogte (height) en lengte (length), waarbij hoogte staande gemeten wordt en lengte liggend.">
				>
				["at0001"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"Op enig tijdstip gemeten lengte.">
				>
				["at0003"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Lengte">
					description = <"De lichaamslengte vanaf de kruin van het hoofd tot en met de voetzool.">
				>
				["at0007"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0011"] = <
					text = <"Apparaat">
					description = <"Beschrijving van het bij de meting gebruikte apparaat.">
				>
				["at0013"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0014"] = <
					text = <"Positie">
					description = <"Positie tijdens de meting, van de gemeten persoon.">
				>
				["at0016"] = <
					text = <"Staand">
					description = <"De lengte is gemeten, staand op beide voeten met het gewicht gelijkmatig verdeeld, hielen tegen elkaar en beide billen en hakken in contact met een verticale achterkant.">
				>
				["at0018"] = <
					text = <"Opmerking">
					description = <"Opmerking over de meting van de lichaamslengte.">
				>
				["at0019"] = <
					text = <"Beïnvloedende factoren">
					description = <"Vermeld ieder probleem of feit die de meting van de lengte beïnvloedt, b.v. notitie maken van een amputatie.">
				>
				["at0020"] = <
					text = <"Liggend">
					description = <"De lengte is liggend gemeten, volledig uitgestrekt, plat bekken, benen gestrekt en voeten gebogen.">
				>
			>
		>
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Height/Length">
					description = <"Height, or body length, is measured from crown of head to sole of foot.  Height is measured with the individual in a standing position and body length in a recumbent position.">
				>
				["at0001"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"Any timed measurement of height or body length.">
				>
				["at0003"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Height/Length">
					description = <"The length of the body from crown of head to sole of foot.">
				>
				["at0007"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0011"] = <
					text = <"Device">
					description = <"Description of the device used to measure height or body length.">
				>
				["at0013"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0014"] = <
					text = <"Position">
					description = <"Position of individual when measured.">
				>
				["at0016"] = <
					text = <"Standing">
					description = <"Height is measured standing on both feet with weight distributed evenly, heels together and both buttocks and heels in contact with a vertical back board.">
				>
				["at0018"] = <
					text = <"Comment">
					description = <"Comment about the measurement of body height/length.">
				>
				["at0019"] = <
					text = <"Confounding factors">
					description = <"Record any issues or factors that may impact on the measurement of body height/length eg noting of amputation.">
				>
				["at0020"] = <
					text = <"Lying">
					description = <"Length is measured in a fully extended, recumbent position with the pelvis flat, legs extended and feet flexed.">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"Größe/Länge">
					description = <"Größe bzw. Körperlänge wird vom Scheitel bis zur Fußsohle gemessen. Größe wird in einer stehenden Position gemessen, Körperlänge in einer liegenden Position.">
				>
				["at0001"] = <
					text = <"History">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"Jede zu einem Zeitpunkt gemessene Körpergröße/-länge.">
				>
				["at0003"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Größe/Länge">
					description = <"Die Länge des Körpers von Scheitel bis Sohle.">
				>
				["at0007"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0011"] = <
					text = <"Gerät">
					description = <"Beschreibung des Geräts, das zur Messung der Größe oder Länge verwendet wurde.">
				>
				["at0013"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0014"] = <
					text = <"Position">
					description = <"Position des Individiums bei der Messung.">
				>
				["at0016"] = <
					text = <"Stehend">
					description = <"Größe wird stehend auf beiden Füßen gemessen, mit dem Gewicht gleichmäßig verteilt, den Hacken zusammen und beiden Gesäßbacken und Hacken in Kontakt mit einem senkrechten Brett.">
				>
				["at0018"] = <
					text = <"Kommentar">
					description = <"Kommentar über die Messung der Körpergröße/-länge.">
				>
				["at0019"] = <
					text = <"Einflussfaktoren">
					description = <"Zur Dokumentation von Faktoren, die sich auf die Messung der Körpergröße/-länge auswirken können, z.B. einer Amputation.">
				>
				["at0020"] = <
					text = <"Liegend">
					description = <"Länge wird in einer voll ausgestreckten, liegenden Position gemessen. Hierbei wird das Becken flach gehalten, die Beine ausgestreckt und die Füße gebeugt.">
				>
			>
		>
		["pt-br"] = <
			items = <
				["at0000"] = <
					text = <"Altura / comprimento">
					description = <"Altura ou comprimento do corpo, é medida a partir da coroa da cabeça a sola do pé.
A altura é medida com o indivíduo na posição de pé e comprimento do corpo na posição decúbito dorsal.">
				>
				["at0001"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Qualquer evento">
					description = <"Medida a qualquer momento da altura ou comprimento do corpo.">
				>
				["at0003"] = <
					text = <"Simple">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Altura / comprimento">
					description = <"O comprimento do corpo da coroa da cabeça a sola do pé.">
				>
				["at0007"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0011"] = <
					text = <"Dispositivo">
					description = <"Descrição do dispositivo utilizado para medir altura ou comprimento do corpo.">
				>
				["at0013"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0014"] = <
					text = <"Posição">
					description = <"Posição individual quando medido.">
				>
				["at0016"] = <
					text = <"De pé">
					description = <"A altura é medida de pé sobre os dois pés com o peso distribuído uniformemente, calcanhares juntos e as nádegas e os calcanhares em contato com uma placa traseira vertical.">
				>
				["at0018"] = <
					text = <"Comentário">
					description = <"Comentário sobre a medição da altura/comprimento do corpo.">
				>
				["at0019"] = <
					text = <"Fatore de erro">
					description = <"Registrar quaisquer problemas ou fatores que possam ter impacto sobre a medição da altura/comprimento do corpo, por exemplo, observação de amputação.">
				>
				["at0020"] = <
					text = <"Decúbito dorsal">
					description = <"O comprimento é medido em uma posição totalmente estendida, deitada com a pelve plana, pernas estendidas e os pés flexionados.">
				>
			>
		>
		["fa"] = <
			items = <
				["at0000"] = <
					text = <"قد و یا طول">
					description = <"قد یا طول بدن از نوک سر تا کف پا اندازه گیری می شود.بلندی در حالت ایستاده و طول بدن فرد در حالت خوابیده اندازه گیری می شود ">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"هر رویداد">
					description = <"اندازه گیری زمانی قد یا طول بدن">
				>
				["at0003"] = <
					text = <"*Simple(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"قد و یا طول">
					description = <"طول فرد از نوک سر تا کف پا ">
				>
				["at0007"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0011"] = <
					text = <"تجهیز">
					description = <"توصیف تجهیز استفاده شده برای اندازه گیری قد یا طول فرد">
				>
				["at0013"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0014"] = <
					text = <"موقعیت">
					description = <"وضعیت فرد در حال اندازه گیری">
				>
				["at0016"] = <
					text = <"ایستاده">
					description = <"قد بصورت ایستاده بر هر دو پا، پاشنه  ها کنار هم ، باسن و پاشنه ها در راستای خط عمودی پشت  با توزیع وزن مساوی اندازه گیری می شود">
				>
				["at0018"] = <
					text = <"نظر">
					description = <"نظر در مورد اندازه گیری قد و یا طول فرد">
				>
				["at0019"] = <
					text = <"فاکتورهای جانبی">
					description = <"ثبت هر گونه مساله یا فاکتوری که ممکن است روی اندازه گیری قد یا طول تاثیر داشته باشه به عنوان مثال ذکر قطع عضو">
				>
				["at0020"] = <
					text = <"خوابیده">
					description = <"  طول در حالت کاملا کشیده و طاقباز با لگن صاف، ساق های کشیده و پاهای جمع شده از مچ پا اندازه گیری می شود">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"الارتفاع / الطول">
					description = <"الارتفاع أو طول الجسم, يتم قياسه من تاج الرأس إلى أخمص القدم. يتم قياس الارتفاع عندما يكون الفرد واقفا, و طول الجسم عندما يكون الفرد مستلقيا.">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"إحدى الوقائع">
					description = <"قياس في لحظة زمنية معينة لطول أو ارتفاع الجسم.">
				>
				["at0003"] = <
					text = <"*Simple(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"الارتفاع / الطول">
					description = <"طول الجسم من تاج الرأس إلى أخمص القدم.">
				>
				["at0007"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0011"] = <
					text = <"الجهيزة">
					description = <"وصف الجهيزة المستخدمة لقياس طول أو ارتفاع الجسم.">
				>
				["at0013"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0014"] = <
					text = <"الوضع">
					description = <"وضع الشخص عند القياس.">
				>
				["at0016"] = <
					text = <"واقف">
					description = <"يتم قياس الارتفاع و الفرد في وضع الوقوف على القدمين مع توزيع الوزن بشكل متساوٍ, و وضع الكعبين متجاورين, و كلا الأليتين متلامستين مع لوح ظهري عمودي.">
				>
				["at0018"] = <
					text = <"تعليق">
					description = <"تعليق حول قياس طول / ارتفاع الجسم.">
				>
				["at0019"] = <
					text = <"العوامل المربكة">
					description = <"لتسجيل أي مسائل أو عوامل قد تؤثر على قياس طول / ارتفاع الجسم, مثل آثار البتر.">
				>
				["at0020"] = <
					text = <"مستلقٍ">
					description = <"يتم قياس الطول في وضع مستلقٍ متمدد بشكل تام مع استواء الحوض, و الأرجل ممتدة و الأقدام مرتخية.">
				>
			>
		>
		["es-ar"] = <
			items = <
				["at0000"] = <
					text = <"Altura/Longitud corporal">
					description = <"La altura o longitud corporal es medida desde la coronilla de la cabeza hasta la planta de los pies. La altura es medida con el individuo en posición erguida y la longitud corporal, en posición recostada.">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"Cualquier evento">
					description = <"Cualquier registro de altura o longitud corporal en un momento determinado.">
				>
				["at0003"] = <
					text = <"*Simple(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Altura/Longitud corporal">
					description = <"La longitud corporal desde la coronilla de la cabeza hasta la planta de los pies.">
				>
				["at0007"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0011"] = <
					text = <"Instrumento">
					description = <"Descripción del dispositivo usado para medir la altura o la longitud corporal.">
				>
				["at0013"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0014"] = <
					text = <"Posición">
					description = <"Posición del individuo durante la medición de estatura.">
				>
				["at0016"] = <
					text = <"De pie">
					description = <"La altura se mide de pie, sobre ambos pies con el peso distribuido en forma homogénea, con los talones juntos y ambos glúteos y talones en contacto con una placa posterior vertical o pared.">
				>
				["at0018"] = <
					text = <"Comentario">
					description = <"Comentario acerca de la medición de la altura/longitud corporal.">
				>
				["at0019"] = <
					text = <"Factores de confusión">
					description = <"Registro de todos las aspectos, condiciones o factores que pueden afectar la medición de la altura/longitud corporal, por ejemplo la amputación de miembros inferiores.">
				>
				["at0020"] = <
					text = <"Acostado">
					description = <"La longitud corporal es medida en una posición recostada y completamente extendida, con la pelvis plana, las piernas extendidas y los pies flexionados.">
				>
			>
		>
	>
```

Pulse (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.pulse.v1

concept
	[at0000]	-- Pulse
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Jasmin Buck, Sebastian Garde">
				["organisation"] = <"University of Heidelberg, Central Queensland University">
			>
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			author = <
				["name"] = <"Vyacheslav Mavrin">
				["organisation"] = <"JSC Comsoft">
			>
		>
	>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"2006-03-26">
	>
	details = <
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"لتسجيل تفاصيل حول معدل و نظم القلب.">
			use = <"يستخدم لتسجيل الخصائص التي تم قياسها فيما يتعلق بمعدل و نظم القلب, بما في ذلك بيان بسيط حول وجود نبض و معدل ضربات القلب. و لا يتم استخدام هذه القراءات بالملاحظة المباشرة للقلب ذاته, و إنما يتنم استنباطها من مصادر بديلة تتضمن التسمع المباشر للقلب أو تخطيط كهربية القلب بما يعكس النشاط الكهربي للقلب.
معدل و نظم القلب ( أو تخصيصهما إلى النبض) عادة ما يتم تسجيلهم على أنهم يمثلون واحدا من العلامات الحياتية – و التي تتكون من ضغط الدم, التنفس, درجة الحرارة, و قياس التأكسج. و يوجد نماذج إضافية مخصصة لكل نوع من هذه المفاهيم.">
			keywords = <"المعدل", "معدل القلب", "النظم">
			misuse = <"لا يستخدم لتسجيل استنتاجات حول معدل و نظم القلب الذي تم قياسهما. و ينبغي تسجيل بيانات مثل (المريض يعاني من الرجفان الأذيني) أو (يعاني من تسرع ضربات القلب) في نماذج أخرى مخصصة و متعلقة بتقييم حالة المريض.
لا تستخدم لتسجيل معدل القلب الميكانيكي, أو النظم أو الخصائص الأخرى – و يتم تسجيل ذلك باستخدام تخصيص لهذا النموذج يسمى ملاحظة. معدل القلب – النبض.
لا يستخدم لتسجيل تفاصيل فحص أو تقييم أكثر شمولا للجهاز القلبي الوريدي. و يمكن أن تستخدم نماذج معينة أخرى لتسجيل خصائص مثل نبض قمة القلب, النفخات, و الموجودات عند التسمع, إلى آخره.
المفاهيم الأخرى مثل أقصى معدل للقلب, أو معدل القلب المستهدف ينبغي أن يتم تسجيلها في نماذج أخرى متعلقة بتقييم المجهود.">
			copyright = <"© openEHR Foundation">
		>
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the measurement of the pulse rate, or heart rate, and description of associated characteristics as one component of a vital signs observation.">
			use = <"Use to record the presence or absence of a pulse rate or heart rate. 

Use to record the measurement of the pulse rate, or heart rate, and observation about the associated rhythm.

Use to record a simple description of characteristics that are associated with the pulse or heart beat, that might be commonly recorded as part of a vital signs obervation.

Measurements such as the maximum pulse or heart rate over an interval of time can be recorded using \"Maximum' event. Others point-in-time or interval events may be specified within a template or at run-time.

In practice, the terms heart rate and pulse rate are often used interchangeably. This archetype allows either term to be used when the measurement site is not specified, to suit clincian preferences.

In certain situations, however, it is important to differentiate between a pulse rate observed at a peripheral artery, such as the radial artery, in contrast to the centrally observed heart rate. This archetype allows the data to be very specific and differentiate between central heart rate and the pulse rate recorded at a specified artery.">
			keywords = <"rate", "rhythm", "beat", "pulse", "heart", "vital", "sign">
			misuse = <"Not to be used to record the R-R rate in the context of an Electrocardiograph report - this is to be recorded using the OBSERVATION.ecg archetype.

Not to be used to record other details of the full cardiovascular examination or assessment. Other specific CLUSTER archetypes will be used to record characteristics such as apex beat, murmurs and bruits, auscultatory findings,

In particular, this archetype is not intended to record the assessment of peripheral vascular disease, which requires documentation of the presence and strength of each peripheral pulse.  A specific CLUSTER archetype will be used to record the general findings on examiantion of peripheral pulses.  

Not to be used to record fetal heart rate - this is recorded using the OBSERVATION.fetal_heart archetype.

Concepts such as Target Heart Rate should be recorded in separate EVALUATION archetypes related to goals and exercise assessment.">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"Zur Dokumentation der Frequenz und des Rhythmus des Herzens.">
			use = <"Zur allgemeinen Dokumentation der Herzfrequenz, besonders der elektrischen Frequenz.">
			keywords = <"Frequenz", "Herzfrequenz", "Rhythmus">
			misuse = <"Zur Dokumentation der mechanischen Frequenz Puls benutzen (OSBSERVATION.heart_reate-pulse.v1).">
			copyright = <"© openEHR Foundation">
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			purpose = <"Для записи информации о частоте  и ритме  сердцечных сокращений.">
			use = <"Используется для записи измеренных характеристик, связанных с темпом и ритма сердца, в том числе простая констатация наличия сердечного ритма. Эти характеристики не регистрируются путем прямого наблюдения самого сердца, а подразумевают альтернативные источники, включая прямую аускультацию сердца или электрокардиограф, отражающий электрическую активность сердца.
Частота и ритм сердечных сокращений  (или специализация этого архетипа - Пульс), как правило, регистрируются в качестве одного из компонентов жизненно важных признаков - включая кровяное давление, дыхание, температуру и оксиметрию. Для каждого из этих понятий существуют специальные архетипы. ">
			keywords = <"ЧСС", "ритм", "сердечный ритм", "частотат сердечных сокращений">
			misuse = <"Не следует использовать для записи выводов о измеряемых частоте и ритме сердечных сокращений. Такого рода заявления, как, например, пациент находится в состоянии фибрилляция предсердий или тахикардии, должны быть записаны в других специальных архетипах, относящихся к категории ОЦЕНКА.
Не следует использовать для записи механической частоты сердечных сокращений, ритма и связанные с ними характеристик - это записывается используя специализацию этого архетипа - OBSERVATION.heart_rate-pulse.
Не используется для записи другой информации обширной системы обследования или оценки сердечно-сосудистой системы. Другие специфические архетипы используются для записи таких характеристик, как верхушечный толчок, шумы, результаты аускультаци и т.д.
Такие понятия, как максимальная или целевая частота сердечных сокращений, должны записываться в отдельных архетипах, предназначенных специально для осуществления оценки.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"CommitteeDraft">
	other_contributors = <"Koray Atalag, University of Auckland, New Zealand", "Rong Chen, Cambio Healthcare Systems, Sweden", "Stephen Chu, NeHTA, Australia", "Angela de Zwart, Orion Health, New Zealand", "Graham Denyer, Australian Antarctic Division, Australia", "Paul Donaldson, Nursing Informatics Australia, Australia", "Sebastian Garde, Ocean Informatics, Germany", "Sam Heard, Ocean Informatics, Australia", "Evelyn Hovenga, EJSH Consulting, Australia", "Eugene Igras, IRIS Systems, Inc., Canada", "Athanasios Kleontas, Ergobyte Informatics, Greece", "Shinji Kobayashi, Ehime University, Japan", "Robert Legan, NEHTA, Australia", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Rohan Martin, Ambulance Victoria, Australia", "Ian McNicoll, Ocean Informatics, United Kingdom (Editor)", "Jeroen Meintjens, Medisch Centrum Alkmaar, Netherlands", "Monica Merchat, Hospital Cardiac Electrophysiology, MS Health Informatics Student, former ICU nurse, former Anesthesia Technician, United States", "Arturo Romero, SESCAM, Spain">
	other_details = <
		["current_contact"] = <"Heather Leslie, Ocean Informatics, heather.leslie@oceaninformatics.com">
		["references"] = <"Direct communication with clinicians.">
		["MD5-CAM-1.0.1"] = <"CA632AFE25F2CAFF4D62EA41C065CEDB">
	>

definition
	OBSERVATION[at0000] matches {	-- Pulse
		data matches {
			HISTORY[at0002] matches {	-- history
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0003] occurrences matches {0..*} matches {	-- Any event
						data matches {
							ITEM_TREE[at0001] matches {	-- structure
								items cardinality matches {0..*; unordered} matches {
									ELEMENT[at1005] occurrences matches {0..1} matches {	-- Pulse Presence
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at1024, 	-- Present
													at1025]	-- Absent
												}
											}
										}
									}
									ELEMENT[at0004] occurrences matches {0..1} matches {	-- Rate
										name matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at1026, 	-- Pulse Rate
													at1027]	-- Heart Rate
												}
											}
										}
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::382]>
												list = <
													["1"] = <
														units = <"/min">
														magnitude = <|>=0.0|>
														precision = <|0|>
													>
												>
											>
										}
									}
									ELEMENT[at0005] occurrences matches {0..1} matches {	-- Regularity
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0006, 	-- Regular
													at1028, 	-- Irregular
													at0007, 	-- Regularly Irregular
													at0008]	-- Irregularly Irregular
												}
											}
										}
									}
									ELEMENT[at1030] occurrences matches {0..*} matches {	-- Character
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at1022] occurrences matches {0..1} matches {	-- Clinical Description
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at1023] occurrences matches {0..*} matches {	-- Clinical Interpretation
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
						state matches {
							ITEM_TREE[at0012] matches {	-- List
								items cardinality matches {0..*; unordered} matches {
									ELEMENT[at0013] occurrences matches {0..1} matches {	-- Position
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at1003, 	-- Standing
													at1001, 	-- Sitting
													at1002, 	-- Reclining
													at1000; 	-- Lying
													at1001]	-- assumed value
												}
											}
										}
									}
									ELEMENT[at1018] occurrences matches {0..1} matches {	-- Confounding Factors
										value matches {
											DV_TEXT matches {*}
										}
									}
									allow_archetype CLUSTER[at1017] occurrences matches {0..*} matches {	-- Exertion
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.level_of_exertion(-[a-zA-Z0-9_]+)*\.v1/}
									}
								}
							}
						}
					}
					INTERVAL_EVENT[at1036] occurrences matches {0..1} matches {	-- Maximum
						math_function matches {
							DV_CODED_TEXT matches {
								defining_code matches {[openehr::144]}
							}
						}
						data matches {
							use_node ITEM_TREE /data[at0002]/events[at0003]/data[at0001]	-- /data[history]/events[Any event]/data[structure]
						}
						state matches {
							use_node ITEM_TREE /data[at0002]/events[at0003]/state[at0012]	-- /data[history]/events[Any event]/state[List]
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0010] matches {	-- List
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at1019] occurrences matches {0..1} matches {	-- Method
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at1032, 	-- Palpation
									at1033, 	-- Auscultation
									at1034]	-- Device
								}
							}
						}
					}
					ELEMENT[at1037] occurrences matches {0..1} matches {	-- Findings Location
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at1038, 	-- Radial Artery - Left
									at1039, 	-- Radial Artery - Right
									at1040, 	-- Heart
									at1041, 	-- Carotid Artery - Left
									at1042, 	-- Carotid Artery - Right
									at1043, 	-- Femoral Artery - Left
									at1044]	-- Femoral Artery - Right
								}
							}
						}
					}
					allow_archetype CLUSTER[at1013] occurrences matches {0..1} matches {	-- Device
						include
							archetype_id/value matches {/openEHR-EHR-CLUSTER\.device(-[a-zA-Z0-9_]+)*\.v1/}
						exclude
							archetype_id/value matches {/.*/}
					}
				}
			}
		}
	}


ontology
	term_definitions = <
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"*Pulse(en)">
					description = <"*Measurement of the pulse rate, or heart rate, and description of associated characteristics.(en)">
				>
				["at0001"] = <
					text = <"*structure(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0003"] = <
					text = <"*Any event(en)">
					description = <"*Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.(en)">
				>
				["at0004"] = <
					text = <"*Rate(en)">
					description = <"*The rate, measured in beats per minute.(en)">
					comment = <"*Run-time name constraints have been specified, in order to simplify the renaming of this data element to Pulse Rate or Heart Rate, as required.(en)">
				>
				["at0005"] = <
					text = <"*Regularity(en)">
					description = <"*The observed regularity of the pulse or heart beat.(en)">
				>
				["at0006"] = <
					text = <"*Regular(en)">
					description = <"*The rhythm is regular.(en)">
				>
				["at0007"] = <
					text = <"*Regularly Irregular(en)">
					description = <"*The rhythm is regularly irregular.(en)">
				>
				["at0008"] = <
					text = <"*Irregularly Irregular(en)">
					description = <"*The rhythm is irregular in a chaotic manner.(en)">
				>
				["at0010"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0012"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0013"] = <
					text = <"*Position(en)">
					description = <"*The body position of the subject during the observation.(en)">
				>
				["at1000"] = <
					text = <"*Lying(en)">
					description = <"*The subject was lying flat.(en)">
				>
				["at1001"] = <
					text = <"*Sitting(en)">
					description = <"*The subject was sitting (for example on bed or chair).(en)">
				>
				["at1002"] = <
					text = <"*Reclining(en)">
					description = <"*The subject was reclining.(en)">
				>
				["at1003"] = <
					text = <"*Standing(en)">
					description = <"*The subject was standing.(en)">
				>
				["at1005"] = <
					text = <"*Pulse Presence(en)">
					description = <"*Identification of a pulse or heart beat.(en)">
					comment = <"*It can be implied that the pulse is present if Rate >0 beats/min.(en)">
				>
				["at1013"] = <
					text = <"*Device(en)">
					description = <"*Details about the device used to observe the pulse or heart beat.(en)">
				>
				["at1017"] = <
					text = <"*Exertion(en)">
					description = <"*Details about physical exertion being undertaken during the examination.(en)">
				>
				["at1018"] = <
					text = <"*Confounding Factors(en)">
					description = <"*Narrative description about any incidental factors that may be affect interpretation of the physical findings.(en)">
					comment = <"*For example, presence of a pacemaker, level of anxiety; pain or fever etc.(en)">
				>
				["at1019"] = <
					text = <"*Method(en)">
					description = <"*Method used to the pulse observe the pulse or heart beat.(en)">
					comment = <"*For example, auscultation or electronic monitoring. (en)">
				>
				["at1022"] = <
					text = <"*Clinical Description(en)">
					description = <"*Narrative description about the findings.(en)">
				>
				["at1023"] = <
					text = <"*Clinical Interpretation(en)">
					description = <"*Single word, phrase or brief description represents the clinical meaning and significance of the pulse or heart beat findings.(en)">
					comment = <"*Coding with a terminology is preferred, where possible. For example: Bradycardia, Extrasystoles or Sinus rhythm. Multiple statements are allowed. (en)">
				>
				["at1024"] = <
					text = <"*Present(en)">
					description = <"*A pulse or heart beat can be detected.(en)">
				>
				["at1025"] = <
					text = <"*Absent(en)">
					description = <"*A pulse or heart beat cannot be detected.(en)">
				>
				["at1026"] = <
					text = <"*Pulse Rate(en)">
					description = <"*The pulse rate, measured in beats per minute.(en)">
				>
				["at1027"] = <
					text = <"*Heart Rate(en)">
					description = <"*The heart rate, measured in beats per minute.(en)">
				>
				["at1028"] = <
					text = <"*Irregular(en)">
					description = <"*The rhythm is irregular.(en)">
				>
				["at1030"] = <
					text = <"*Character(en)">
					description = <"*Description of the character of the pulse or heart beat.(en)">
					comment = <"*Coding with a terminology is desired, where possible. For example: full, thready, bounding, slow rising, or collapsing. Multiple terms may be recorded.(en)">
				>
				["at1032"] = <
					text = <"*Palpation(en)">
					description = <"*The findings are observed by physical touch of the observer on the subject.(en)">
				>
				["at1033"] = <
					text = <"*Auscultation(en)">
					description = <"*The findings are observed with the assistance of a device, such as a stethoscope.(en)">
				>
				["at1034"] = <
					text = <"*Device(en)">
					description = <"*The pulse findings are observed using a device, such as a pulse oximeter or cardiac monitor.(en)">
				>
				["at1036"] = <
					text = <"*Maximum(en)">
					description = <"*Maximum rate of the pulse or heart beat observed during a period of exertion.(en)">
				>
				["at1037"] = <
					text = <"*Findings Location(en)">
					description = <"*Body site where the pulse or heart beat findings were observed.(en)">
				>
				["at1038"] = <
					text = <"*Radial Artery - Left(en)">
					description = <"*The left radial artery.(en)">
				>
				["at1039"] = <
					text = <"*Radial Artery - Right(en)">
					description = <"*The right radial artery.(en)">
				>
				["at1040"] = <
					text = <"*Heart(en)">
					description = <"*The region of the heart.(en)">
				>
				["at1041"] = <
					text = <"*Carotid Artery - Left(en)">
					description = <"*The left carotid artery.(en)">
				>
				["at1042"] = <
					text = <"*Carotid Artery - Right(en)">
					description = <"*The right carotid artery.(en)">
				>
				["at1043"] = <
					text = <"*Femoral Artery - Left(en)">
					description = <"*The left femoral artery.(en)">
				>
				["at1044"] = <
					text = <"*Femoral Artery - Right(en)">
					description = <"*The right femoral artery.(en)">
				>
			>
		>
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Pulse">
					description = <"Measurement of the pulse rate, or heart rate, and description of associated characteristics.">
				>
				["at0001"] = <
					text = <"structure">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"Any event">
					description = <"Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.">
				>
				["at0004"] = <
					text = <"Rate">
					description = <"The rate, measured in beats per minute.">
					comment = <"Run-time name constraints have been specified, in order to simplify the renaming of this data element to Pulse Rate or Heart Rate, as required.">
				>
				["at0005"] = <
					text = <"Regularity">
					description = <"The observed regularity of the pulse or heart beat.">
				>
				["at0006"] = <
					text = <"Regular">
					description = <"The rhythm is regular.">
				>
				["at0007"] = <
					text = <"Regularly Irregular">
					description = <"The rhythm is regularly irregular.">
				>
				["at0008"] = <
					text = <"Irregularly Irregular">
					description = <"The rhythm is irregular in a chaotic manner.">
				>
				["at0010"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0012"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0013"] = <
					text = <"Position">
					description = <"The body position of the subject during the observation.">
				>
				["at1000"] = <
					text = <"Lying">
					description = <"The subject was lying flat.">
				>
				["at1001"] = <
					text = <"Sitting">
					description = <"The subject was sitting (for example on bed or chair).">
				>
				["at1002"] = <
					text = <"Reclining">
					description = <"The subject was reclining.">
				>
				["at1003"] = <
					text = <"Standing">
					description = <"The subject was standing.">
				>
				["at1005"] = <
					text = <"Pulse Presence">
					description = <"Identification of a pulse or heart beat.">
					comment = <"It can be implied that the pulse is present if Rate >0 beats/min.">
				>
				["at1013"] = <
					text = <"Device">
					description = <"Details about the device used to observe the pulse or heart beat.">
				>
				["at1017"] = <
					text = <"Exertion">
					description = <"Details about physical exertion being undertaken during the examination.">
				>
				["at1018"] = <
					text = <"Confounding Factors">
					description = <"Narrative description about any incidental factors that may be affect interpretation of the physical findings.">
					comment = <"For example, presence of a pacemaker, level of anxiety; pain or fever etc.">
				>
				["at1019"] = <
					text = <"Method">
					description = <"Method used to the pulse observe the pulse or heart beat.">
					comment = <"For example, auscultation or electronic monitoring. ">
				>
				["at1022"] = <
					text = <"Clinical Description">
					description = <"Narrative description about the findings.">
				>
				["at1023"] = <
					text = <"Clinical Interpretation">
					description = <"Single word, phrase or brief description represents the clinical meaning and significance of the pulse or heart beat findings.">
					comment = <"Coding with a terminology is preferred, where possible. For example: Bradycardia, Extrasystoles or Sinus rhythm. Multiple statements are allowed. ">
				>
				["at1024"] = <
					text = <"Present">
					description = <"A pulse or heart beat can be detected.">
				>
				["at1025"] = <
					text = <"Absent">
					description = <"A pulse or heart beat cannot be detected.">
				>
				["at1026"] = <
					text = <"Pulse Rate">
					description = <"The pulse rate, measured in beats per minute.">
				>
				["at1027"] = <
					text = <"Heart Rate">
					description = <"The heart rate, measured in beats per minute.">
				>
				["at1028"] = <
					text = <"Irregular">
					description = <"The rhythm is irregular.">
				>
				["at1030"] = <
					text = <"Character">
					description = <"Description of the character of the pulse or heart beat.">
					comment = <"Coding with a terminology is desired, where possible. For example: full, thready, bounding, slow rising, or collapsing. Multiple terms may be recorded.">
				>
				["at1032"] = <
					text = <"Palpation">
					description = <"The findings are observed by physical touch of the observer on the subject.">
				>
				["at1033"] = <
					text = <"Auscultation">
					description = <"The findings are observed with the assistance of a device, such as a stethoscope.">
				>
				["at1034"] = <
					text = <"Device">
					description = <"The pulse findings are observed using a device, such as a pulse oximeter or cardiac monitor.">
				>
				["at1036"] = <
					text = <"Maximum">
					description = <"Maximum rate of the pulse or heart beat observed during a period of exertion.">
				>
				["at1037"] = <
					text = <"Findings Location">
					description = <"Body site where the pulse or heart beat findings were observed.">
				>
				["at1038"] = <
					text = <"Radial Artery - Left">
					description = <"The left radial artery.">
				>
				["at1039"] = <
					text = <"Radial Artery - Right">
					description = <"The right radial artery.">
				>
				["at1040"] = <
					text = <"Heart">
					description = <"The region of the heart.">
				>
				["at1041"] = <
					text = <"Carotid Artery - Left">
					description = <"The left carotid artery.">
				>
				["at1042"] = <
					text = <"Carotid Artery - Right">
					description = <"The right carotid artery.">
				>
				["at1043"] = <
					text = <"Femoral Artery - Left">
					description = <"The left femoral artery.">
				>
				["at1044"] = <
					text = <"Femoral Artery - Right">
					description = <"The right femoral artery.">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"*Pulse(en)">
					description = <"*Measurement of the pulse rate, or heart rate, and description of associated characteristics.(en)">
				>
				["at0001"] = <
					text = <"Structure">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"History">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"*Any event(en)">
					description = <"*Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.(en)">
				>
				["at0004"] = <
					text = <"*Rate(en)">
					description = <"*The rate, measured in beats per minute.(en)">
					comment = <"*Run-time name constraints have been specified, in order to simplify the renaming of this data element to Pulse Rate or Heart Rate, as required.(en)">
				>
				["at0005"] = <
					text = <"*Regularity(en)">
					description = <"*The observed regularity of the pulse or heart beat.(en)">
				>
				["at0006"] = <
					text = <"*Regular(en)">
					description = <"*The rhythm is regular.(en)">
				>
				["at0007"] = <
					text = <"*Regularly Irregular(en)">
					description = <"*The rhythm is regularly irregular.(en)">
				>
				["at0008"] = <
					text = <"*Irregularly Irregular(en)">
					description = <"*The rhythm is irregular in a chaotic manner.(en)">
				>
				["at0010"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0012"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0013"] = <
					text = <"*Position(en)">
					description = <"*The body position of the subject during the observation.(en)">
				>
				["at1000"] = <
					text = <"*Lying(en)">
					description = <"*The subject was lying flat.(en)">
				>
				["at1001"] = <
					text = <"*Sitting(en)">
					description = <"*The subject was sitting (for example on bed or chair).(en)">
				>
				["at1002"] = <
					text = <"*Reclining(en)">
					description = <"*The subject was reclining.(en)">
				>
				["at1003"] = <
					text = <"*Standing(en)">
					description = <"*The subject was standing.(en)">
				>
				["at1005"] = <
					text = <"*Pulse Presence(en)">
					description = <"*Identification of a pulse or heart beat.(en)">
					comment = <"*It can be implied that the pulse is present if Rate >0 beats/min.(en)">
				>
				["at1013"] = <
					text = <"*Device(en)">
					description = <"*Details about the device used to observe the pulse or heart beat.(en)">
				>
				["at1017"] = <
					text = <"*Exertion(en)">
					description = <"*Details about physical exertion being undertaken during the examination.(en)">
				>
				["at1018"] = <
					text = <"*Confounding Factors(en)">
					description = <"*Narrative description about any incidental factors that may be affect interpretation of the physical findings.(en)">
					comment = <"*For example, presence of a pacemaker, level of anxiety; pain or fever etc.(en)">
				>
				["at1019"] = <
					text = <"*Method(en)">
					description = <"*Method used to the pulse observe the pulse or heart beat.(en)">
					comment = <"*For example, auscultation or electronic monitoring. (en)">
				>
				["at1022"] = <
					text = <"*Clinical Description(en)">
					description = <"*Narrative description about the findings.(en)">
				>
				["at1023"] = <
					text = <"*Clinical Interpretation(en)">
					description = <"*Single word, phrase or brief description represents the clinical meaning and significance of the pulse or heart beat findings.(en)">
					comment = <"*Coding with a terminology is preferred, where possible. For example: Bradycardia, Extrasystoles or Sinus rhythm. Multiple statements are allowed. (en)">
				>
				["at1024"] = <
					text = <"*Present(en)">
					description = <"*A pulse or heart beat can be detected.(en)">
				>
				["at1025"] = <
					text = <"*Absent(en)">
					description = <"*A pulse or heart beat cannot be detected.(en)">
				>
				["at1026"] = <
					text = <"*Pulse Rate(en)">
					description = <"*The pulse rate, measured in beats per minute.(en)">
				>
				["at1027"] = <
					text = <"*Heart Rate(en)">
					description = <"*The heart rate, measured in beats per minute.(en)">
				>
				["at1028"] = <
					text = <"*Irregular(en)">
					description = <"*The rhythm is irregular.(en)">
				>
				["at1030"] = <
					text = <"*Character(en)">
					description = <"*Description of the character of the pulse or heart beat.(en)">
					comment = <"*Coding with a terminology is desired, where possible. For example: full, thready, bounding, slow rising, or collapsing. Multiple terms may be recorded.(en)">
				>
				["at1032"] = <
					text = <"*Palpation(en)">
					description = <"*The findings are observed by physical touch of the observer on the subject.(en)">
				>
				["at1033"] = <
					text = <"*Auscultation(en)">
					description = <"*The findings are observed with the assistance of a device, such as a stethoscope.(en)">
				>
				["at1034"] = <
					text = <"*Device(en)">
					description = <"*The pulse findings are observed using a device, such as a pulse oximeter or cardiac monitor.(en)">
				>
				["at1036"] = <
					text = <"*Maximum(en)">
					description = <"*Maximum rate of the pulse or heart beat observed during a period of exertion.(en)">
				>
				["at1037"] = <
					text = <"*Findings Location(en)">
					description = <"*Body site where the pulse or heart beat findings were observed.(en)">
				>
				["at1038"] = <
					text = <"*Radial Artery - Left(en)">
					description = <"*The left radial artery.(en)">
				>
				["at1039"] = <
					text = <"*Radial Artery - Right(en)">
					description = <"*The right radial artery.(en)">
				>
				["at1040"] = <
					text = <"*Heart(en)">
					description = <"*The region of the heart.(en)">
				>
				["at1041"] = <
					text = <"*Carotid Artery - Left(en)">
					description = <"*The left carotid artery.(en)">
				>
				["at1042"] = <
					text = <"*Carotid Artery - Right(en)">
					description = <"*The right carotid artery.(en)">
				>
				["at1043"] = <
					text = <"*Femoral Artery - Left(en)">
					description = <"*The left femoral artery.(en)">
				>
				["at1044"] = <
					text = <"*Femoral Artery - Right(en)">
					description = <"*The right femoral artery.(en)">
				>
			>
		>
		["ru"] = <
			items = <
				["at0000"] = <
					text = <"*Pulse(en)">
					description = <"*Measurement of the pulse rate, or heart rate, and description of associated characteristics.(en)">
				>
				["at0001"] = <
					text = <"Дерево">
					description = <"@ внутреннийl @">
				>
				["at0002"] = <
					text = <"История">
					description = <"@ внутреннийl @">
				>
				["at0003"] = <
					text = <"*Any event(en)">
					description = <"*Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.(en)">
				>
				["at0004"] = <
					text = <"*Rate(en)">
					description = <"*The rate, measured in beats per minute.(en)">
					comment = <"*Run-time name constraints have been specified, in order to simplify the renaming of this data element to Pulse Rate or Heart Rate, as required.(en)">
				>
				["at0005"] = <
					text = <"*Regularity(en)">
					description = <"*The observed regularity of the pulse or heart beat.(en)">
				>
				["at0006"] = <
					text = <"*Regular(en)">
					description = <"*The rhythm is regular.(en)">
				>
				["at0007"] = <
					text = <"*Regularly Irregular(en)">
					description = <"*The rhythm is regularly irregular.(en)">
				>
				["at0008"] = <
					text = <"*Irregularly Irregular(en)">
					description = <"*The rhythm is irregular in a chaotic manner.(en)">
				>
				["at0010"] = <
					text = <"Дерево">
					description = <"@ внутреннийl @">
				>
				["at0012"] = <
					text = <"Дерево">
					description = <"@ внутреннийl @">
				>
				["at0013"] = <
					text = <"*Position(en)">
					description = <"*The body position of the subject during the observation.(en)">
				>
				["at1000"] = <
					text = <"*Lying(en)">
					description = <"*The subject was lying flat.(en)">
				>
				["at1001"] = <
					text = <"*Sitting(en)">
					description = <"*The subject was sitting (for example on bed or chair).(en)">
				>
				["at1002"] = <
					text = <"*Reclining(en)">
					description = <"*The subject was reclining.(en)">
				>
				["at1003"] = <
					text = <"*Standing(en)">
					description = <"*The subject was standing.(en)">
				>
				["at1005"] = <
					text = <"*Pulse Presence(en)">
					description = <"*Identification of a pulse or heart beat.(en)">
					comment = <"*It can be implied that the pulse is present if Rate >0 beats/min.(en)">
				>
				["at1013"] = <
					text = <"*Device(en)">
					description = <"*Details about the device used to observe the pulse or heart beat.(en)">
				>
				["at1017"] = <
					text = <"*Exertion(en)">
					description = <"*Details about physical exertion being undertaken during the examination.(en)">
				>
				["at1018"] = <
					text = <"*Confounding Factors(en)">
					description = <"*Narrative description about any incidental factors that may be affect interpretation of the physical findings.(en)">
					comment = <"*For example, presence of a pacemaker, level of anxiety; pain or fever etc.(en)">
				>
				["at1019"] = <
					text = <"*Method(en)">
					description = <"*Method used to the pulse observe the pulse or heart beat.(en)">
					comment = <"*For example, auscultation or electronic monitoring. (en)">
				>
				["at1022"] = <
					text = <"*Clinical Description(en)">
					description = <"*Narrative description about the findings.(en)">
				>
				["at1023"] = <
					text = <"*Clinical Interpretation(en)">
					description = <"*Single word, phrase or brief description represents the clinical meaning and significance of the pulse or heart beat findings.(en)">
					comment = <"*Coding with a terminology is preferred, where possible. For example: Bradycardia, Extrasystoles or Sinus rhythm. Multiple statements are allowed. (en)">
				>
				["at1024"] = <
					text = <"*Present(en)">
					description = <"*A pulse or heart beat can be detected.(en)">
				>
				["at1025"] = <
					text = <"*Absent(en)">
					description = <"*A pulse or heart beat cannot be detected.(en)">
				>
				["at1026"] = <
					text = <"*Pulse Rate(en)">
					description = <"*The pulse rate, measured in beats per minute.(en)">
				>
				["at1027"] = <
					text = <"*Heart Rate(en)">
					description = <"*The heart rate, measured in beats per minute.(en)">
				>
				["at1028"] = <
					text = <"*Irregular(en)">
					description = <"*The rhythm is irregular.(en)">
				>
				["at1030"] = <
					text = <"*Character(en)">
					description = <"*Description of the character of the pulse or heart beat.(en)">
					comment = <"*Coding with a terminology is desired, where possible. For example: full, thready, bounding, slow rising, or collapsing. Multiple terms may be recorded.(en)">
				>
				["at1032"] = <
					text = <"*Palpation(en)">
					description = <"*The findings are observed by physical touch of the observer on the subject.(en)">
				>
				["at1033"] = <
					text = <"*Auscultation(en)">
					description = <"*The findings are observed with the assistance of a device, such as a stethoscope.(en)">
				>
				["at1034"] = <
					text = <"*Device(en)">
					description = <"*The pulse findings are observed using a device, such as a pulse oximeter or cardiac monitor.(en)">
				>
				["at1036"] = <
					text = <"*Maximum(en)">
					description = <"*Maximum rate of the pulse or heart beat observed during a period of exertion.(en)">
				>
				["at1037"] = <
					text = <"*Findings Location(en)">
					description = <"*Body site where the pulse or heart beat findings were observed.(en)">
				>
				["at1038"] = <
					text = <"*Radial Artery - Left(en)">
					description = <"*The left radial artery.(en)">
				>
				["at1039"] = <
					text = <"*Radial Artery - Right(en)">
					description = <"*The right radial artery.(en)">
				>
				["at1040"] = <
					text = <"*Heart(en)">
					description = <"*The region of the heart.(en)">
				>
				["at1041"] = <
					text = <"*Carotid Artery - Left(en)">
					description = <"*The left carotid artery.(en)">
				>
				["at1042"] = <
					text = <"*Carotid Artery - Right(en)">
					description = <"*The right carotid artery.(en)">
				>
				["at1043"] = <
					text = <"*Femoral Artery - Left(en)">
					description = <"*The left femoral artery.(en)">
				>
				["at1044"] = <
					text = <"*Femoral Artery - Right(en)">
					description = <"*The right femoral artery.(en)">
				>
			>
		>
	>

```

Respiration (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.respiration.v1

concept
	[at0000]	-- Respirations
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Jasmin Buck, Sebastian Garde">
				["organisation"] = <"University of Heidelberg, Central Queensland University">
			>
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"?">
			>
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			author = <
				["name"] = <"Shahla Foozonkhah">
				["organisation"] = <"Ocean Informatics">
			>
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			author = <
				["name"] = <"Dr. Leonardo Der Jachadurian">
				["organisation"] = <"Bitios.com">
			>
			accreditation = <"Medical Doctor (Internal Medicine Specialist)">
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			author = <
				["name"] = <"Marja Buur">
				["organisation"] = <"Medisch Centrum Alkmaar">
				["email"] = <"m.buur-krom@mca.nl">
			>
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			author = <
				["name"] = <"Carlos Porto Filho">
				["organisation"] = <"USP">
			>
		>
	>
description
	original_author = <
		["name"] = <"Ian McNicoll">
		["organisation"] = <"Ocean Informatics, United Kingdom">
		["email"] = <"ian.mcnicoll@oceaninformatics.com">
		["date"] = <"2009-07-17">
	>
	details = <
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			purpose = <"Registrar as características da respiração espontânea.">
			use = <"Usar para registrar as características observadas e medidas relacionadas com as respirações espontâneas em uma pessoa, incluindo frequência respiratória, profundidade e ritmo.

As respirações são comumente registradas como um componente de sinais vitais - incluindo pressão arterial, pulso, temperatura e oximetria. Há arquétipo específicos adicionais para cada um desses conceitos.

As respirações devem ser medidas antes de refeições em recém-nascidos e crianças jovens.">
			keywords = <"*respirações(pt-BR)", "*respirando(pt-BR)", "*respiração(pt-BR)", "*resps(en)", "*respiração(pt-BR)">
			misuse = <"Não usar para tentar registrar outros aspectos de exame respiratório em geral. Outros arquétipos específicos serão utilizados para registrar características tais como esforço respiratório, achados auscultatórios, etc.

Não usar para registrar detalhes quando o paciente está sob ventilação assistida.">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"لتسجيل الخصائص الملاحظة - المشاهدة - للتنفس التلقائي">
			use = <"يستخدم لتسجيل الخصائص الملاحظة - المشاهدة - أو التي يتم قياسها فيما يتعلق بالتنفس التلقائي لدى الشخص, بما فيه معدل  ( سرعة) التنفس, عمق التنفس و نَظْمه.

عادة ما يتم تسجيل التنفس كجزء من العلامات الحياتية - و التي تتكون من ضغط الدم, النبض, درجة الحرارة و قياس التأكسج. و يوجد بالفعل نماذج مخصوصة إضافية لكل من هذه المفاهيم.

ينبغي قياس التنفس قبل الإطعام في حديثي الولادة و الرضع الصغار">
			keywords = <"*respirations(en)", "*breathing(en)", "*breath(en)", "*resps(en)", "*respiration(en)">
			misuse = <"لا يمكن استخدام النموذج لمحاولة تسجيل الجوانب الأخرى من الفحص أو التقييم التنفسي أشمل. يمكن استخدام نماذج أخرى مخصصة لتسجيل الخصائص من المجهود التنفسي و الموجودات التسمعية, إلى آخره
 لا يستخدم لتسجيل تفاصيل حالة المنريض إذا كان يخضع للتهوية المساعَدة">
			copyright = <"© openEHR Foundation">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			purpose = <"Para registrar las características de la respiración espontánea.">
			use = <"Usar para registrar las características observadas y medidas, relacionadas con la respiraciones espontáneas en una persona, incluyendo frecuencia respiratoria, profundidad y ritmo.

Las respiraciones son comúnmente registradas como un componente de los signos vitales (los cuales abarcan la presión arterial, el pulso, la temperatura y la oximetría de pulso). Hay arquetipos específicos adicionales para cada uno de esos conceptos.

Las respiraciones deberían ser medidas antes de las comidas en neonatos e infantes jóvenes.">
			keywords = <"respiraciones", "respiración", "FR">
			misuse = <"No usar para intentar registrar otros aspectos del exámen respiratorio en general. Otros arquetipos específicos serán utilizados para registrar características tales como esfuerzo respiratorio, hallazgos auscultatorios, etc.

No usar para registrar detalles cuando el paciente está en ventilación asistida.">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"Zur Dokumentation der Frequenz, des Rhythmus und der Charakteristik der Atmung">
			use = <"">
			keywords = <"Atmung", "Respiration">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the observed characteristics of spontaneous breathing.">
			use = <"Use to record the observed and measured characteristics related to spontaneous respirations in a person, including respiratory rate, depth and rhythm.

Respirations are commonly recorded as one component of Vital signs - comprising Blood Pressure, Pulse, Temperature, and Oximetry.  There are additional specific archetypes for each of these concepts.

Respirations should be measured before feeds in neonates and young infants.">
			keywords = <"respirations", "breathing", "breath", "resps", "respiration">
			misuse = <"Not to be used to try to record other aspects of the broader respiratory examination or assessment.  Other specific archetypes will be used to record characteristics such as respiratory effort, auscultatory findings etc.

Not to be used to record details  when the subject is undergoing assisted ventilation.">
			copyright = <"© openEHR Foundation">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			purpose = <"برای ثبت ویژگی هایی قابل مشاهده تنفس خود بخود بکار می رود.">
			use = <"برای ثبت ویژگی هایی قابل مشاهده و قابل اندازه گیری مربوط به تنفس خود بخود فرد ، شامل میزان تنفس ، عمق و ریتم استفاده می شود.
تنفسها معمولا به عنوان یکی از مولفه های علایم حیاتی ثبت می شوند -شامل فشار خون ، نبض ، درجه حرارت واندازه گیری اکسیژن.
در نوزادان و شیر خواران اندازه گیری تنفس قبل از تغذیه اندازه گیری می شود  .

">
			keywords = <"تنفسها", "نفس کشیده", "نفس", "تنفسی">
			misuse = <"برای ثبت سایر جنبه های آزمایشات یا ارزیابی گسترده تر تنفسی استفاده نمی شود.
از سایر الگوسازهای تخصصی برای ثبت ویژگی هایی نظیر تلاش برای تنفس،یافته های شنیداری و غیره استفاده نمایید.
برای ثبت جزییات در زمانی که فرد تحت تنفس مصنوعی است استفاده نکنید .  ">
			copyright = <"© openEHR Foundation">
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			purpose = <"Om observaties van de spontane ademhaling te registreren ">
			use = <"Wordt gebruikt om observaties en metingen te registreren, die gerelateerd zijn aan de spontane ademhaling van een persoon, inclusief ademhalingsfrequentie, diepte en ritme

Ademhaling wordt gewoonlijk geregistreerd als onderdeel van de vitale functies - bestaande uit bloeddruk, temperatuur en zuurstofsaturatie. Er zijn aanvullende specifieke archetypes voor deze concepten.

De ademhaling moet bij neonaten en jonge kinderen gemeten worden voor de voeding.">
			keywords = <"ademhaling", "respiratie", "inademen", "uitademen", "ademteug", "adem", "ademen">
			misuse = <"Niet te gebruiken om andere aspecten van het uitgebreidere onderzoek of beoordeling van de ademhaling te registreren. Andere, specifieke archetypes zullen gebruikt worden om karakteristieken zoals ademhalingsinspanning en auscultatoire bevindingen te registreren.

Niet te gebruiken voor de registratie van details, als de persoon beademing ondergaat.
">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Marja Buur, Medisch Centrum Alkmaar/ Code24, Netherlands", "Gregory Caulton, PatientOS Inc., United States", "Stephen Chu, NeHTA, Australia", "Sebastian Garde, Ocean Informatics, Germany", "Anne Harbison, CPCER, Australia", "Sam Heard, Ocean Informatics, Australia", "Omer Hotomaroglu, Turkey", "Sundaresan Jagannathan, Scottish NHS, United Kingdom", "Andrew James, University of Toronto, Canada", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Rikard Lovstrom, Swedish Medical Association, Sweden", "Ian McNicoll, Ocean Informatics, United Kingdom (Editor)", "Jeroen Meintjens, Medisch Centrum Alkmaar, Netherlands", "Soon Ghee Yap, Singapore Health Services Pte Ltd, Singapore">
	other_details = <
		["references"] = <"Braun RB.  Respiratory Rate and Pattern. In: Walker HK, Hall WD, Hurst JW. Clinical methods: the history, physical, and laboratory examinations. [Internet] 3rd ed. Stoneham (MA): Butterworth Publishers; c1990 [cited 2009 Jul 21] 
Available from: http://www.ncbi.nlm.nih.gov/bookshelf/br.fcgi?book=cm&part=A1308 [Accessed July 22, 2009].

Gaunt AC, Frang T. Examination of the Respiratory System. The Journal of Clinical Examination 2007 (4): 14-22 
Available from:   http://www.thejce.com/downloads/journals/oct_2007/14-22%20Gaunt%20and%20Frang%20-%20Respiratory%20System.pdf  [Accessed July 22, 2009]

Cheyne-Stokes respiration - Wikipedia, the free encyclopedia [Internet]. [cited 2009 Jul 25 ] 
Available from: http://en.wikipedia.org/wiki/Cheyne-Stokes_respiration

Biot's respiration - Wikipedia, the free encyclopedia [Internet]. [cited 2009 Jul 25 ] 
Available from: http://en.wikipedia.org/wiki/Biot%27s_respiration

Apneustic respirations - Wikipedia, the free encyclopedia [Internet]. [cited 2009 Jul 25 ] 
Available from: http://en.wikipedia.org/wiki/Apneustic_respirations">
		["MD5-CAM-1.0.1"] = <"F785361CE72E20207CD557387B49B703">
	>

definition
	OBSERVATION[at0000] matches {	-- Respirations
		data matches {
			HISTORY[at0001] matches {	-- history
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0002] occurrences matches {0..*} matches {	-- Any event
						data matches {
							ITEM_TREE[at0003] matches {	-- List
								items cardinality matches {0..*; unordered} matches {
									ELEMENT[at0004] occurrences matches {0..1} matches {	-- Rate
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::382]>
												list = <
													["1"] = <
														units = <"/min">
														magnitude = <|0.0..200.0|>
														precision = <|0|>
													>
												>
											>
										}
									}
									ELEMENT[at0005] occurrences matches {0..1} matches {	-- Rhythm
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0006, 	-- Regular
													at0007]	-- Irregular
												}
											}
										}
									}
									ELEMENT[at0016] occurrences matches {0..1} matches {	-- Depth
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0017, 	-- Normal
													at0018, 	-- Shallow
													at0019, 	-- Deep
													at0025]	-- Variable
												}
											}
										}
									}
									ELEMENT[at0024] occurrences matches {0..1} matches {	-- Description
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0009] occurrences matches {0..1} matches {	-- Abnormal respiratory pattern
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0012, 	-- Kussmaul's respiration
													at0030, 	-- Cheyne-Stokes respiration
													at0031, 	-- Ataxic respiration
													at0033, 	-- Apneustic respiration
													at0034, 	-- Cluster breathing
													at0044, 	-- Apnoea
													at0054]	-- Prolonged expiratory phase
												}
											}
											DV_TEXT matches {*}
										}
									}
								}
							}
						}
						state matches {
							ITEM_TREE[at0022] matches {	-- List
								items cardinality matches {0..*; unordered} matches {
									allow_archetype CLUSTER[at0055] occurrences matches {0..1} matches {	-- Ambient oxygen
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.ambient_oxygen(-[a-zA-Z0-9_]+)*\.v1/}
									}
									ELEMENT[at0056] occurrences matches {0..*} matches {	-- Confounding factors
										value matches {
											DV_TEXT matches {*}
										}
									}
									allow_archetype CLUSTER[at0037] occurrences matches {0..1} matches {	-- Exertion
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.level_of_exertion(-[a-zA-Z0-9_]+)*\.v1/}
									}
								}
							}
						}
					}
				}
			}
		}
	}


ontology
	term_definitions = <
		["pt-br"] = <
			items = <
				["at0000"] = <
					text = <"Respirações">
					description = <"As características observadas da respiração espontânea como seria comumente registrada como parte de uma observação de um \"sinal vital\".">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"Qualquer evento">
					description = <"Evento genérico">
				>
				["at0003"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Frequência">
					description = <"Frequência respiratória">
				>
				["at0005"] = <
					text = <"Ritmo">
					description = <"Ritmo respiratório">
				>
				["at0006"] = <
					text = <"Regular">
					description = <"Respiração regular">
				>
				["at0007"] = <
					text = <"Irregular">
					description = <"Respiração irregular">
				>
				["at0009"] = <
					text = <"Padrão respiratório anormal">
					description = <"Padrão específico de respiração anormal. Outros padrões podem ser colocados como texto livre ou subconjunto terminológico definido no nível da especialização ou no nível do template.">
				>
				["at0012"] = <
					text = <"Respiração de Kussmaul">
					description = <"Respiração profunda com ou sem suspiro.">
				>
				["at0016"] = <
					text = <"Profundidade">
					description = <"Pronfundidade respiratória">
				>
				["at0017"] = <
					text = <"Normal">
					description = <"Profundidade respiratória normal">
				>
				["at0018"] = <
					text = <"Superficial">
					description = <"Profundidade respiratória superficial">
				>
				["at0019"] = <
					text = <"Profunda">
					description = <"Respiração profunda">
				>
				["at0022"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0024"] = <
					text = <"Descrição">
					description = <"A descrição textual das respirações">
				>
				["at0025"] = <
					text = <"Variável">
					description = <"Profundidade respiratória variável">
				>
				["at0030"] = <
					text = <"Respiração de Cheyne-Stokes">
					description = <"Períodos de hiperventilação alternados com períodos de apneia.">
				>
				["at0031"] = <
					text = <"Respiração atáxica">
					description = <"Respiração de frequência e volume corrente variáveis">
				>
				["at0033"] = <
					text = <"Respiração apneustica">
					description = <"Profunda, inspiração com suspiro com uma pausa na inspiração total seguida de uma breve insuficiência na expiração.">
				>
				["at0034"] = <
					text = <"Respiração de Biot">
					description = <"Grupos de respirações profundas irregulares que se alternam com períodos de apneia.">
				>
				["at0037"] = <
					text = <"Esforço">
					description = <"Nível de esforço durante ou logo antes de ser feita a observação. Destinada apenas para registrar o esforço somente se isso pode afetar as respirações e onde normalmente não seria registrado com parte de uma observação clínica geral.">
				>
				["at0044"] = <
					text = <"Apneia.">
					description = <"Parada da respiração.">
				>
				["at0054"] = <
					text = <"Expiração prolongada">
					description = <"A fase da expiração é mais longa que o normal/usual. Associada com doenças obstrutivas das vias respiratórias tais como asma.">
				>
				["at0055"] = <
					text = <"Oxigênio ambiente">
					description = <"Detalhes da quantidade de oxigênio sendo administrada ao paciente no momento da observação. Se assumem valores de concentração de oxigênio de 21%, Fi02 de 0,21 e velocidade de fluxo do oxigênio de 0 l/min ou 0 ml/min.">
				>
				["at0056"] = <
					text = <"Fatores de confundimento">
					description = <"Comenta e registra outros fatores incidentais que podem contribuir para as respirações observadas. Por exemplo, nível de ansiedade, dor, alimentação em crianças, traqueostomia, etc.">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"التنفس">
					description = <"الخصائص الملحوظة - المشاهدة- للتنفس التلقائي و الذي عادة ما يتم تسجيله كجزء من فحص العلامات الحياتية">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"إحدى الوقائع">
					description = <"حدث - واقعة - جنيسة / غير محدود الملكية">
				>
				["at0003"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"السرعة - المعدَّل">
					description = <"سرعة (معدل) التنفس">
				>
				["at0005"] = <
					text = <"النَّظم">
					description = <"نَظم التنفس">
				>
				["at0006"] = <
					text = <"منتظم">
					description = <"تنفس منتظم">
				>
				["at0007"] = <
					text = <"غير منتظم">
					description = <"تنفس غير منتظم">
				>
				["at0009"] = <
					text = <"النمط التنفسي غير الطبيعي">
					description = <"نمط تنفسي غير طبيعي معيّن. يمكن إدخال الأنماط الأخرى على هيئة نص حر أو على هيئة فرع من المصطلحات يتم تعريفها على مستوى النماذج المخصصة أو القوالب.">
				>
				["at0012"] = <
					text = <"تنفس كوسماول">
					description = <"تنفس صدري عميق بوجود أو بعدم وجود لُهاث مرئي">
				>
				["at0016"] = <
					text = <"العمق">
					description = <"عمق التنفس">
				>
				["at0017"] = <
					text = <"طبيعي">
					description = <"عمق التنفس طبيعي">
				>
				["at0018"] = <
					text = <"ضحل">
					description = <"عمق التنفس ضحل">
				>
				["at0019"] = <
					text = <"عميق">
					description = <"التنفس عميق">
				>
				["at0022"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0024"] = <
					text = <"الوصف">
					description = <"نص يصف التنفس">
				>
				["at0025"] = <
					text = <"متغير">
					description = <"عمق التنفس متغيِّر">
				>
				["at0030"] = <
					text = <"تنفس شيين - ستوكس">
					description = <"فترات من فرط التهوية متبادلة مع فترات من انقطاع النفس">
				>
				["at0031"] = <
					text = <"تنفس رَنَحي - فاقد للانتظام">
					description = <"التنفس بسرعات (معدلات) و أحجام مَدِّية مختلفة">
				>
				["at0033"] = <
					text = <"تنفس بشهيق مستمر">
					description = <"شهيق عميق مع اللُّهاث, مع توقف عند الشهيق الكلي يليه إطلاق للنفس بشكل مختصر و غير كافي">
				>
				["at0034"] = <
					text = <"*Cluster breathing(en)">
					description = <"*Clusters of irregular breaths that alternate with periods of apnoea. Also termed Biot's breathing.(en)">
				>
				["at0037"] = <
					text = <"المجهود - عنقود">
					description = <"مستوى إجهاد الشخص عند تسجيل الملاحظة أو قبل تسجيلها بقليل. يستخدم فقط لتسجيل الإجهاد حيث قد يؤثر على التنفس حيث لن يتم تسجيله بشكل طبيعي كجزء من الملاحظات السريرية العامة  ">
				>
				["at0044"] = <
					text = <"*Apnoea(en)">
					description = <"*Breathing has ceased.(en)">
				>
				["at0054"] = <
					text = <"*Prolonged expiratory phase(en)">
					description = <"*The respiratory expiratory phase is longer than normal/usual. Associated with obstructive airways disease such as asthma.(en)">
				>
				["at0055"] = <
					text = <"الأكسجين المحيط - عنقود">
					description = <"*Details of the amount of oxygen being delivered to the subject at the time of observation.  Assumed values of 21% oxygen concentration, Fi02 of 0.21 and oxygen flow rate of 0 l/min or 0 ml/min.(en)">
				>
				["at0056"] = <
					text = <"العوامل المُربِكة">
					description = <"تعليق على و تسجيل للعوامل العارضة التي قد تؤثر في ملاحظة التنفس. مثلا, مستوى القلق, الألم, الإطعام لدى الرُّضع, الفــغــر الرُّغامي">
				>
			>
		>
		["es-ar"] = <
			items = <
				["at0000"] = <
					text = <"Respiraciones">
					description = <"Las características observadas de la respiración espontánea, tal cual sería comúnmente registrada como parte de una evaluación de signos vitales.">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"Cualquier evento">
					description = <"Evento genérico">
				>
				["at0003"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Frecuencia">
					description = <"Frecuencia respiratoria.">
				>
				["at0005"] = <
					text = <"Ritmo">
					description = <"Ritmo de la respiración.">
				>
				["at0006"] = <
					text = <"Regular">
					description = <"Respiración regular.">
				>
				["at0007"] = <
					text = <"Irregular">
					description = <"Respiración irregular.">
				>
				["at0009"] = <
					text = <"Patrones respiratorios anormales">
					description = <"Patrón respiratorio anormal específico. Otros patrones pueden ser ingresados como texto libre o un subconjunto terminológico, definido a nivel de la especialización o de la plantilla.">
				>
				["at0012"] = <
					text = <"Respiración de Kussmaul">
					description = <"Respiración profunda con o sin jadeo visible.">
				>
				["at0016"] = <
					text = <"Profundidad">
					description = <"Profundidad de la respiración.">
				>
				["at0017"] = <
					text = <"Normal">
					description = <"Respiración con profundidad normal.">
				>
				["at0018"] = <
					text = <"Superficial">
					description = <"Respiración superficial.">
				>
				["at0019"] = <
					text = <"Profunda">
					description = <"Respiración profunda.">
				>
				["at0022"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0024"] = <
					text = <"Descripción">
					description = <"La descripción textual de las respiraciones.">
				>
				["at0025"] = <
					text = <"Variable">
					description = <"Respiración con profundidad variable.">
				>
				["at0030"] = <
					text = <"Respiración de Cheyne-Stokes">
					description = <"Períodos de hiperventilación alternando con períodos de apnea.">
				>
				["at0031"] = <
					text = <"Respiración atáxica">
					description = <"Respiración de frecuencia y volumen corriente variables.">
				>
				["at0033"] = <
					text = <"Respiración apnéustica">
					description = <"Respiración profunda, con jadeo inspiratorio, que tiene una pausa al completar la inspiración, seguida con una espiración breve e insuficiente.">
				>
				["at0034"] = <
					text = <"Respiración de Biot">
					description = <"Grupos de respiraciones irregulares profundas que alternan con períodos de apnea.">
				>
				["at0037"] = <
					text = <"Esfuerzo">
					description = <"Nivel de esfuerzo del sujeto justo antes o en el momento en que la observación está siendo hecha. Destinado para registrar el esfuerzo solo si puede afectar las respiraciones y donde normalmente no sería registrado como parte de una observación clínica general.">
				>
				["at0044"] = <
					text = <"Apnea">
					description = <"Cesación de la respiración.">
				>
				["at0054"] = <
					text = <"Espiración prolongada">
					description = <"La fase espiratoria respiratoria es mas larga que lo usual/normal. Asociada con enfermedades obstructivas de las vías aéreas tales como el asma.">
				>
				["at0055"] = <
					text = <"Oxígeno ambiental">
					description = <"Especificación de la cantidad de oxígeno siendo administrada al sujeto al momento de la observación. Se asumen valores de concentración de oxígeno de 21%, FiO2 de 0,21 y una velocidad de flujo de oxígeno de 0 lt/min o 0 ml/min.">
				>
				["at0056"] = <
					text = <"Factores confundidores">
					description = <"Comenta y registra otros factores incidentales que pueden contribuir a las respiraciones observadas. Por ejemplo, el nivel de ansiedad, dolor, alimentación previa en infantes, traqueostomía, etc.">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"*Respirations(en)">
					description = <"*The observed characteristics of spontaneous breathing as would commonly be recorded as part of a 'vital signs' examination.(en)">
				>
				["at0001"] = <
					text = <"History">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"allgemeines Ereignis">
				>
				["at0003"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"*Rate(en)">
					description = <"*Rate of respiration.(en)">
				>
				["at0005"] = <
					text = <"*Rhythm(en)">
					description = <"*Rhythm of respiration.(en)">
				>
				["at0006"] = <
					text = <"*Regular(en)">
					description = <"*Regular respiration.(en)">
				>
				["at0007"] = <
					text = <"*Irregular(en)">
					description = <"*Irregular respirations.(en)">
				>
				["at0009"] = <
					text = <"*Abnormal respiratory pattern(en)">
					description = <"*Specific abnormal respiratory pattern. Other patterns may be entered as free text or terminology subset defined at specialisation or template level.(en)">
				>
				["at0012"] = <
					text = <"*Kussmaul's respiration(en)">
					description = <"*Deep chest breathing with or without a visible gasp.(en)">
				>
				["at0016"] = <
					text = <"*Depth(en)">
					description = <"*Depth of respiration.(en)">
				>
				["at0017"] = <
					text = <"*Normal(en)">
					description = <"*Normal depth of breathing.(en)">
				>
				["at0018"] = <
					text = <"*Shallow(en)">
					description = <"*Shallow depth of breathing.(en)">
				>
				["at0019"] = <
					text = <"*Deep(en)">
					description = <"*Deep breathing.(en)">
				>
				["at0022"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0024"] = <
					text = <"*Description(en)">
					description = <"*A text description of respirations.(en)">
				>
				["at0025"] = <
					text = <"*Variable(en)">
					description = <"*Variable depth of breathing.(en)">
				>
				["at0030"] = <
					text = <"*Cheyne-Stokes respiration(en)">
					description = <"*Periods of hyperventilation alternating with periods of apnoea.(en)">
				>
				["at0031"] = <
					text = <"*Ataxic respiration(en)">
					description = <"*Breathing of varying tidal volumes and rates.(en)">
				>
				["at0033"] = <
					text = <"*Apneustic respiration(en)">
					description = <"*Deep, gasping inspiration with a pause at full inspiration followed by a brief, insufficient release of breath.(en)">
				>
				["at0034"] = <
					text = <"*Cluster breathing(en)">
					description = <"*Clusters of irregular breaths that alternate with periods of apnoea. Also termed Biot's breathing.(en)">
				>
				["at0037"] = <
					text = <"*Exertion(en)">
					description = <"*Subject's level of exertion at or just prior to the observation being made. Intended only to record exertion only as it might effect respirations and where it would not normally be recorded as part of general clinical observation.(en)">
				>
				["at0044"] = <
					text = <"*Apnoea(en)">
					description = <"*Breathing has ceased.(en)">
				>
				["at0054"] = <
					text = <"*Prolonged expiratory phase(en)">
					description = <"*The respiratory expiratory phase is longer than normal/usual. Associated with obstructive airways disease such as asthma.(en)">
				>
				["at0055"] = <
					text = <"*Ambient oxygen(en)">
					description = <"*Details of the amount of oxygen being delivered to the subject at the time of observation.  Assumed values of 21% oxygen concentration, Fi02 of 0.21 and oxygen flow rate of 0 l/min or 0 ml/min.(en)">
				>
				["at0056"] = <
					text = <"*Confounding factors(en)">
					description = <"*Comment on and record other incidental factors that may be contributing to the respirations observation. For example, level of anxiety, pain, feeding in infants, tracheostomy.(en)">
				>
			>
		>
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Respirations">
					description = <"The observed characteristics of spontaneous breathing as would commonly be recorded as part of a 'vital signs' examination.">
				>
				["at0001"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"Generic event.">
				>
				["at0003"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Rate">
					description = <"Rate of respiration.">
				>
				["at0005"] = <
					text = <"Rhythm">
					description = <"Rhythm of respiration.">
				>
				["at0006"] = <
					text = <"Regular">
					description = <"Regular respiration.">
				>
				["at0007"] = <
					text = <"Irregular">
					description = <"Irregular respirations.">
				>
				["at0009"] = <
					text = <"Abnormal respiratory pattern">
					description = <"Specific abnormal respiratory pattern. Other patterns may be entered as free text or terminology subset defined at specialisation or template level.">
				>
				["at0012"] = <
					text = <"Kussmaul's respiration">
					description = <"Deep chest breathing with or without a visible gasp.">
				>
				["at0016"] = <
					text = <"Depth">
					description = <"Depth of respiration.">
				>
				["at0017"] = <
					text = <"Normal">
					description = <"Normal depth of breathing.">
				>
				["at0018"] = <
					text = <"Shallow">
					description = <"Shallow depth of breathing.">
				>
				["at0019"] = <
					text = <"Deep">
					description = <"Deep breathing.">
				>
				["at0022"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0024"] = <
					text = <"Description">
					description = <"A text description of respirations.">
				>
				["at0025"] = <
					text = <"Variable">
					description = <"Variable depth of breathing.">
				>
				["at0030"] = <
					text = <"Cheyne-Stokes respiration">
					description = <"Periods of hyperventilation alternating with periods of apnoea.">
				>
				["at0031"] = <
					text = <"Ataxic respiration">
					description = <"Breathing of varying tidal volumes and rates.">
				>
				["at0033"] = <
					text = <"Apneustic respiration">
					description = <"Deep, gasping inspiration with a pause at full inspiration followed by a brief, insufficient release of breath.">
				>
				["at0034"] = <
					text = <"Cluster breathing">
					description = <"Clusters of irregular breaths that alternate with periods of apnoea. Also termed Biot's breathing.">
				>
				["at0037"] = <
					text = <"Exertion">
					description = <"Subject's level of exertion at or just prior to the observation being made. Intended only to record exertion only as it might effect respirations and where it would not normally be recorded as part of general clinical observation.">
				>
				["at0044"] = <
					text = <"Apnoea">
					description = <"Breathing has ceased.">
				>
				["at0054"] = <
					text = <"Prolonged expiratory phase">
					description = <"The respiratory expiratory phase is longer than normal/usual. Associated with obstructive airways disease such as asthma.">
				>
				["at0055"] = <
					text = <"Ambient oxygen">
					description = <"Details of the amount of oxygen being delivered to the subject at the time of observation.  Assumed values of 21% oxygen concentration, Fi02 of 0.21 and oxygen flow rate of 0 l/min or 0 ml/min.">
				>
				["at0056"] = <
					text = <"Confounding factors">
					description = <"Comment on and record other incidental factors that may be contributing to the respirations observation. For example, level of anxiety, pain, feeding in infants, tracheostomy.">
				>
			>
		>
		["fa"] = <
			items = <
				["at0000"] = <
					text = <"تنفس">
					description = <" ویژگی های قابل مشاهده مربوط به تنفس خود بخود که معمولا می توان به عنوان بخشی از آزمایشات \"علایم حیاتی\" ثبت نمود.">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"هر رویداد">
					description = <"رویداد عمومی">
				>
				["at0003"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"میزان">
					description = <"میزان تنفس.">
				>
				["at0005"] = <
					text = <"ریتم">
					description = <"ریتم تنفس.">
				>
				["at0006"] = <
					text = <"منظم">
					description = <"تنفس منظم.">
				>
				["at0007"] = <
					text = <"نامنظم">
					description = <"تنفس نامنظم.">
				>
				["at0009"] = <
					text = <"الگوی غیر طبیعی تنفس">
					description = <"الگوی غیر طبیعی تنفس خاص.سایر الگوها ممکن است به صورت متن آزاد یا زیر مجموعه واژه شناسی تعریف شده در موارد تخصصی یا در سطح الگو استفاده شوند.">
				>
				["at0012"] = <
					text = <"تنفس کاسمال">
					description = <"تنفس عمیق قفسه سینه ای با یا بدون نفسهای بریده بریده. ">
				>
				["at0016"] = <
					text = <"عمق">
					description = <"عمق تنفس.">
				>
				["at0017"] = <
					text = <"طبیعی">
					description = <"عمق تنفس طبیعی.">
				>
				["at0018"] = <
					text = <"سطحی">
					description = <"عمق تنفس سطحی.">
				>
				["at0019"] = <
					text = <"عمیق">
					description = <"تنفس عمیق.">
				>
				["at0022"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0024"] = <
					text = <"توصیف">
					description = <"متنی که تنفسها را توصیف می کند.">
				>
				["at0025"] = <
					text = <"متغیر">
					description = <"عمق تنفس طبیعی.">
				>
				["at0030"] = <
					text = <"تنفس چیین استوکس">
					description = <"دوره های تخلیه عمیق نفس که با دوره های تنگی تنفس تغییر می کند. ">
				>
				["at0031"] = <
					text = <"تنفس بدون قاعده">
					description = <"تنفس متغیر از نظر حجم و میزان.">
				>
				["at0033"] = <
					text = <"تنفس اپناستیک">
					description = <"تنفس بریده بریده و  عمیق با توقف در تنفس کامل که با تنفس ناکافی و کوتاه دنبال می شود. ">
				>
				["at0034"] = <
					text = <"تنفس خوشه ای ">
					description = <"خوشه هایی از تنفس نامنظم که با دوره هایی از تنگی تنفس تغییر می کند. همچنین به عنوان تنفس بیوت شناخته می شود.">
				>
				["at0037"] = <
					text = <"تقلا">
					description = <"سطح تقلای فرد در یا قبل انجام مشاهدات . هدف تنها ثبت فقط تقلایی است که ممکن است تنفس را تحت تاثیر قرار دهد و جایی که به عنوان بخشی از مشاهدات عمومی بالینی ثبت شود ">
				>
				["at0044"] = <
					text = <"تنگی تنفس">
					description = <"تنفس متوقف شده است.">
				>
				["at0054"] = <
					text = <"مرحله بازدم طولانی مدت">
					description = <"مرحله بازدم طولانی مدت که اط حالت طبیعی و معمول .که با بیماری انسداد راههای تنفسی نظیر آسم همراه است. ">
				>
				["at0055"] = <
					text = <"اکسیژن محیطی">
					description = <"جزییات مقدار اکسیژن داده شده به فرد در زمان مشاهده به فرد داده شده است .ارزش فرض شده  غلظت 21 درصدی ااکسیژن و .....از 021 ومیان جریان اکسیژن    است      ">
				>
				["at0056"] = <
					text = <"فاکتورهای جانبی">
					description = <"نظر و ثبت سایر فاکتورهای اتفاقی که ممکن است در مشاهده تنفس شرکت داشته باشند .برای مثال سطح اضطراب ، تغذیه در شیر خوار و تراکئوستومی ">
				>
			>
		>
		["nl"] = <
			items = <
				["at0000"] = <
					text = <"Ademhaling">
					description = <"Observaties van de spontane ademhaling, zoals deze meestal geregistreerd worden als onderdeel van de observatie van de vitale functies">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"any event">
					description = <"Algemene gebeurtenis">
				>
				["at0003"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Frequentie">
					description = <"Ademhalingsfrequentie">
				>
				["at0005"] = <
					text = <"Ritme">
					description = <"Ademhalingsritme">
				>
				["at0006"] = <
					text = <"Regelmatig">
					description = <"Regelmatige ademhaling
">
				>
				["at0007"] = <
					text = <"Onregelmatig">
					description = <"Onregelmatige ademhaling">
				>
				["at0009"] = <
					text = <"Afwijkend ademhalingspatroon">
					description = <"Specifieke abnormaal ademhalingspatronen. Andere patronen kunnen worden genoteerd als vrije tekst of als terminologie deelverzameling, welke gedefinieerd wordt op specialisatie of template niveau.">
				>
				["at0012"] = <
					text = <"Ademhaling volgens Kussmaul">
					description = <"Zeer diepe regelmatige ademhaling ">
				>
				["at0016"] = <
					text = <"Diepte">
					description = <"De diepte van de ademteugen">
				>
				["at0017"] = <
					text = <"Normaal">
					description = <"Normale diepte van de in- en uitademing">
				>
				["at0018"] = <
					text = <"Oppervlakkig">
					description = <"Oppervlakkige ademhaling">
				>
				["at0019"] = <
					text = <"Diep">
					description = <"Diepe ademhaling">
				>
				["at0022"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0024"] = <
					text = <"Beschrijving">
					description = <"Tekstuele beschrijving van de ademhaling.">
				>
				["at0025"] = <
					text = <"Variabel">
					description = <"Variabele diepte van de ademteugen">
				>
				["at0030"] = <
					text = <"Ademhaling volgens Cheyne-Stokes">
					description = <"Periodes van hyperventilatie afwisselend met periodes met apneu">
				>
				["at0031"] = <
					text = <"Atactische ademhaling">
					description = <"Ademhaling met variërende volumes per teug en variërende frequentie">
				>
				["at0033"] = <
					text = <"Apneustische ademhaling">
					description = <"Diepe, hijgende inspiratie met een pauze bij volledige inspiratie, gevolgd door een korte, onvoldoende uitademing.">
				>
				["at0034"] = <
					text = <"Cluster ademhaling">
					description = <"Clusters van onregelmatige ademhaling die worden afgewisseld met perioden van apneu. Ook genoemd ademhaling van Biot.">
				>
				["at0037"] = <
					text = <"Inspanning">
					description = <"Het niveau van inspanning door de persoon, op of net voor het moment van de observatie. Slechts bedoeld om inspanning te registreren die effect kan hebben op de ademhaling en die normaal gesproken niet zou worden geregistreerd als onderdeel van de algemene klinische observatie.">
				>
				["at0044"] = <
					text = <"Apneu">
					description = <"Ademhaling is gestopt.">
				>
				["at0054"] = <
					text = <"Verlengde expiratoire fase">
					description = <"De respiratoire expiratoire fase is langer dan normaal / gebruikelijk. Wordt geassocieerd met obstructieve ziektes van de  luchtwegen, zoals astma.">
				>
				["at0055"] = <
					text = <"Toegevoerde zuurstof">
					description = <"Details van de hoeveelheid zuurstof die wordt geleverd aan de persoon op het moment van waarneming. Veronderstelde waarden van 21% zuurstof, Fi02 van 0,21 en zuurstof levering van 0 l / min of 0 ml / min.">
				>
				["at0056"] = <
					text = <"Beïnvloedende factoren">
					description = <"Opmerking over bijkomende factoren die de ademhaling kunnen beïnvloeden. Bijvoorbeeld, het niveau van angst, pijn, voeding bij zuigelingen, tracheostomie.">
				>
			>
		>
	>

```

Body Mass Index (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.body_mass_index.v1

concept
	[at0000]	-- Body mass index
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["fa"] = <
			language = <[ISO_639-1::fa]>
			author = <
				["name"] = <"Shahla Foozonkhah">
				["organisation"] = <"Ocean Informatics">
				["email"] = <"shahla.foozonkhah@oceaninformatics.com">
			>
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			author = <
				["name"] = <"Marja Buur">
				["organisation"] = <"Medisch Centrum Alkmaar">
				["email"] = <"m.buur-krom@mca.nl">
			>
			accreditation = <"Nurse Informatics">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			author = <
				["name"] = <"Domingo Liotta">
				["organisation"] = <"Universidad de Morón">
			>
			accreditation = <"Universidad de Morón">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			author = <
				["name"] = <"Marco Borges">
				["organisation"] = <"P2D">
				["email"] = <"marco.borges@p2d.com.br">
			>
			accreditation = <"P2D Health Advisor Council">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
	>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"22/03/2006">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record the Body Mass Index (BMI) of a person.
Body Mass Index is a calculated ratio describing how an individual's body weight relates to the weight that is regarded as normal, or desirable, for the individual's height. ">
			use = <"Use to record the Body Mass Index of both adults and children.  
Use to enter the Body Mass Index either manually (ie calculated and directly entered by the clinician), or automatically (ie calculation and entry is done automatically by a software application, based on separate height and weight measurements).
Formulas: Body Mass Index is commonly calculated as weight (kg) / [height (m) squared]. This is the assumed formula unless otherwise specified in the Formula element within Protocol. Alternatively estimate Body Mass Index using pounds and inches: weight (lb) / [height (in) squared] x 703 (with ounces (oz) and fractions changed to decimal values).
In some situations the Body Mass Index formula is corrected eg for use in amputees - this specific formula can be recorded as part of the protocol.  Alternatively the common Body Mass Index calculation can be used with amputees and similar injuries or disabilities if using adjusted height and/or adjusted weight, as appropriate, rather than actual height and weight.   See openEHR-EHR-OBSERVATION.height-adjusted and openEHR-EHR-OBSERVATION.body_weight-adjusted.
See WHO reference re adjusting height/length for Body Mass Index in paediatrics. 
In children and teens, BMI needs to be assessed using age-related reference charts. 
">
			keywords = <"obesity", "index", "body mass", "BMI", "anorexia", "Quetelet", "malnutrition", "failure to thrive", "bulimia">
			misuse = <"Not intended to record information regarding Body Mass Index percentiles - these will be recorded in separate archetypes.">
			copyright = <"© openEHR Foundation">
		>
		["nl"] = <
			language = <[ISO_639-1::nl]>
			purpose = <"Het registreren van de Body Mass Index (BMI) van een persoon.
De Body Mass Index is een berekening hoe het lichaamsgewicht van een persoon zich verhoudt tot het normale gewicht, of gewenste gewicht, t.o.v. de  lengte van de persoon. ">
			use = <"Wordt gebruikt voor het registreren van de Body Mass Index van zowel volwassenen als kinderen. 
Wordt gebruikt door de Body Mass Index of manueel (d.w.z. berekend en direct ingevoerd door de clinicus), of automatisch (d.w.z. dat de berekening en invoer automatisch door een software applicatie, gebaseerd op afzonderlijke lengte en gewicht metingen gedaan wordt) in te voeren.
Formule: Body Mass Index wordt gewoonlijk berekend door gewicht (kg)/[lengte (m) in het kwadraat]. Dit is de veronderstelde formule, tenzij anders gespecificeerd in het Formule element in Protocol.
Alternatieve geschatte Body Mass Index gebruik makend van pounds en inches: gewicht (lb)/[lengte(in) in het kwadraat] x 703 (met ounces (oz) en gedeeltes gewijzigd tot op de decimaal).
In sommige situaties wordt de Body Mass Index formule gecorrigeerd, b.v. voor gebruik bij geamputeerden - deze specifieke formule kan geregistreerd worden als onderdeel van het protocol. Alternatief kan de gewoonlijke Body Mass Index berekening gebruikt worden bij geamputeerden en vergelijkbare verwondingen of handicaps, bij gebruikmaking van aangepaste gewicht en/of lengte in plaats van de werkelijke lengte en gewicht. Gebruik daarvoor openEHR-EHR-OBSERVATION.height-adjusted (openEHR-EHR-OBSERVATION.lengte-aangepast)  en openEHR-EHR-OBSERVATION.body_weight-adjusted (openEHR-EHR-OBSERVATION.lichaamsgewicht-aangepast).
Zie de WHO richtlijnen tot aanpassing van hoogte / lengte voor Body Mass Index in de pediatrie.
Bij kinderen en tieners, dient de BMI te worden beoordeeld met behulp van leeftijd-gerelateerde referentie lijsten.">
			keywords = <"obesitas", "indexbody mass", "BMI", "anorexia", "Quetelet", "ondervoeding", "onvermogen op gewicht te blijven, onvermogen om te groeien", "boulimia">
			misuse = <"Niet bestemd voor het registreren van informatie over de Body Mass Index percentielen - deze zullen worden opgenomen in afzonderlijke archetypen.">
			copyright = <"© openEHR Foundation">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			purpose = <"Para gravar o Índice de Massa Corpórea (IMC) de uma pessoa.
Índice de Massa Corpórea é uma taxa calculada que descreve como o peso corporal de um indivíduo se relaciona com o peso que é considerado normal, ou desejável, para a altura do indivíduo.">
			use = <"Usado para gravar o Índice de Massa Corpórea de adultos e crianças.
Use para registrar o IMC manualmente (isto é, calculado e digitado pelo médico) ou automaticamente (cálculo feito automaticamente por uma aplicação de software, com base na altura e medições de peso).
Fórmulas: IMC é normalmente calculado como peso (kg) / [altura (m) ao quadrado]. Esta é a fórmula assimuda salvo nova fórmula registrada no protocolo. O IMC pode ser medido com libras e polegadas: Peso (lb) / [altura (polegadas) ao quadrado ] x 703 (com onças (oz) e frações alterando casas decimais).
Em algumas situações, a fórmula do IMC é corrigida por exemplo, para uso em pacientes amputados - esta fórmula específica podem ser contabilizados como parte do protocolo. para essa  alternativa de IMC usada com amputados, lesões semelhantes ou deficiência ajusta-se a altura e/ou peso, conforme o caso. Veja openEHR-EHR-OBSERVATION.height-adjusted e OBSERVATION.body_weight-adjusted.
Veja na referência ajustamentos da altura / comprimento para o IMC em pediatria.
Em crianças e adolescentes, o IMC deve ser avaliada por meio de tabelas de referência relacionadas com a idade.">
			keywords = <"obesidade", "índice", "massa corporal", "IMC", "anorexia", "*Quetelet(en)", "subnutrição", "subdesenvolvimento", "bulimia">
			misuse = <"Não se destina a registrar informações sobre os percentis de IMC - estes serão gravadas em arquétipos distintos.">
			copyright = <"© openEHR Foundation">
		>
		["fa"] = <
			language = <[ISO_639-1::fa]>
			purpose = <" برای ثبت شاخص توده بدن فرد  بکار می رود 
شاخص توده بدن نسبتی است که نحوه ارتباط وزن بدن با وزن طبیعی یا مورد دلخواه، با توجه به قد فرد را محاسبه می کند که بصورت وزن طبیعی یا مطلوب فرد در نظر گرفته می شود     ">
			use = <" برای ثبت شاخص توده بدن بزرگسالان و کودکان بکار می رود برای وارد کردن شاخص توده بدن بصورت دستی(توسط افراد بالینی محاسبه و بطور مستقیم ثبت می شود) یا بطور خودکار (محاسبات بطور خودکار توسط نرم افزار و بر اساس اندازه های جداگانه قد و وزن انجام می شود) محاسبه و ثبت می شود.ء
فرمولها : شاخص توده بدن معمولا بصورت وزن بر حسب کیلو گرم تقسیم بر [قد بر حسب متر به توان دو] محاسبه می شود. در محاسبات همیشه فرض بر این فرمول است مگر اینکه عناصر فرمول در پروتکل مدنظر مشخص شوند. همچنین بعنوان فرمولی جایگزین برای تخمین شاخص توده بدن از پوند و اینچ نیز استفاده می شود : وزن بر حسب پوند تقسیم بر [قد بر حسب اینچ به توان دو] ضرب در 703 (مقادیر کسری بصورت اعشاری تغییر می یابند).
شاخص توده بدن برای بکار گیری در شرایطی همچون قطع عضو تصحیح می شود ،این فرمول را می توان بصورت بخشی از پروتکل ثبت نمود. بعنوان فرمولی جایگزین، می توان از فرمول شاخص توده بدن، با تاثیر دادن قد یا وزن معادل (تطبیق یافته) عضو معیوب به جای قد یا وزن واقعی، در موارد قطع عضو و صدمات مشابه یا ناتوانی ها، نیز استفاده کرد.ء
ببینید:ء
openEHR-EHR-OBSERVATION.height-adjusted  وopenEHR-EHR-OBSERVATION.body_weight-adjusted.
مرجع سازمان جهانی بهداشت در مورد استفاده از وزن و یا قد برای شاخص توده بدن در اطفال را بینید.
در بچه ها و نوجوانان لازم است شاخص توده بدن با استفاده از جدول مرجع سن مربوطه محاسبه شود
  ">
			keywords = <"چاقی", "شاخص", "توده بدن", "شاخص توده بدن", "بی اشتهایی", "اندکس کوت لت(شاخص توده بدن)", "سو تغذیه", "اختلال رشد", "پرخوری">
			misuse = <" برای ثبت اطلاعات در مورد شاخص توده بدن به درصد در نظر گرفته نشده است-  این موارد در الگو ساز جداگانه ای ثبت خواهد شد">
			copyright = <"© openEHR Foundation">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			purpose = <"Registrar el Índice de Masa Corporal (IMC) de un individuo.
El Índice de Masa Corporal  es una cociente que describe la manera en que el peso de un individuo se considera normal, o deseable, respecto a su altura. ">
			use = <"Usar para registrar el Índice de Masa Corporal de adultos y niños.
Usar para ingresar el Índice de Masa Corporal manualmente (ej: calculado e ingresado directamente por el médico), o automáticamente (ej: cálculo y entrada se realiza automáticamente por una aplicación de software, basado en la medición de peso y altura por separado).
Fórmulas: Índice de Masa Corporal comúnmente se calcula como peso (kg) / [altura (m) al cuadrado].  Este es la fórmula asumida a menos que se especifique otra en el elemento Fórmula dentro de Protocolo. Otras alternativas estiman el Índice de Masa Corporal usando libras y pulgadas: peso (lb) / [altura (in) al cuadrado) x 703 (con onzas (oz) y fracciones ajustados a valores decimales).
En algunas situaciones la fórmula de Índice de Masa Corporal se corrige por ej: para el uso de amputados - esa fórmula específica puede registrarse como parte del protocolo. Alternativamente el cálculo de Índice de Masa Corporal puede ser usado con amputados y similares o personas con discapacidades si se usa 'altura ajustada' y/o 'peso ajustado' apropiadamente en lugar de altura y peso actual. Véase openEHR-EHR-OBSERVATION.height-adjusted and openEHR-EHR-OBSERVATION.body_weight-adjusted. 
Véase las recomendaciones de la OMS respecto a adecuar peso/altura para el Índice se Masa Corporal en pediatría.
En niños y adolescentes, IMC debe calcularse usando cartillas de referencia por edades.">
			keywords = <"obesidad(sp)", "índice(sp)", "masa corporal(sp)", "IMC(sp)", "anorexia(sp)", "Quetelet(sp)", "malnutrición(sp)", "bulimia(sp)", "desnutrición(sp)">
			misuse = <"No se usa para el registro de percentiles de Índice de Masa Corporal - estos se registran en otros arquetipos por separado.">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"لتسجيل معامل كتلة الجسم للشخص.
معامل كتلة الجسم هو نسبة محسوبة تصف العلاقة بين وزن جسم الشخص و الوزن الطبيعي أو المرغوب المناسب لطول الجسم.">
			use = <"يستخدم لتسجيل معامل كتلة الجسم لكل من البالغين و الأطفال.

يستخدم لإدخال معامل كتلة الجسم المحسوب بشكل يدوي (محسوب و مسَجَّل بشكل مباشر بواسطة الطبيب السريري) أو تلقائيا (يتم الحساب و الإدخال تلقائيا من خلال برنامج كمبيوتر, على أساس قياسات منفردة للطول و الوزن)

الصيَغ: عادة ما يتم حساب معامل كتلة الجسم بقسمة الوزن بالكيلوغرام على مربع الطول بالميتر المربع.

و هذه هي الصيغة المفترضة ما لم يتم تحديد خلاف ذلك في البروتوكول المستخدم.

و يمكن تقدير معامل كتلة الجسم باستخدام الباوند و البوصة : بقسمة الوزن بالباوند على مربع الطول بالبوصة المربعة و ضرب الناتج في 307 - - مع تحويل الأونصات و الكسور الحسابية إلى قيم عشرية.

في بعض المواقف يتم تصحيح معامل كتلة الجسم, مثلا عند استخدامه في الأشخاص الذين يعانون من بتر في أي من الأعضاء - و يمكن استخدام هذه الصيغة الخاصة كجزء من البروتوكول.
كما يمكن استخدام الصيغة الشهيرة لحساب معامل كتلة الجسم للأشخاص الذين يعانون من البرت أو من إصابات أو إعاقات مشابهة إذا تم استخدام قياسات مصححة للطول و/أو الوزن, حيثما كان مناسبا, بدلا من الطول أو الوزن الحقيقين. 
يمكن الرجوع إلى نموذج ملاحظة. الطول المصحح و نموذج ملاحظة. وزن الجسم المصحح.

يمكن الرجوع إلى مرجع منظمة الصحة العالمية لتصحيح قياسات الطول و الوزن لقياس معامل كتلة الجسم في الأطفال.
في الأطفال و المراهقين, توجد حاجة لتقييم معامل كتلة الجسم باستخدام المخطط المرجعي المرتبط بالعمر.">
			keywords = <"*Quetelet(en)", "السمنة", "معامل", "كتلة الجسم", "معامل كتلة الجسم", "فقدان الشهية", "سوء التغذية", "الفشل في النماء", "النُّهام">
			misuse = <"لا يستخدم لتسجيل المعلومات الخاصة بالشرائح المئوية لمعامل كتلة الجسم - حيث يتم تسجيلها في نماذج منفردة.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"Published">
	other_contributors = <"Marja Buur, Medisch Centrum Alkmaar, Netherlands", "Rong Chen, Cambio Healthcare Systems, Sweden", "Angela de Zwart, Orion Health, New Zealand", "Paul Donaldson, Nursing Informatics Australia, Australia", "Sebastian Garde, Ocean Informatics, Germany", "Heather Grain, Llewelyn Grain Informatics, Australia", "Anne Harbison, CPCER, Australia", "Sam Heard, Ocean Informatics, Australia", "Andrew James, University of Toronto, Canada", "Shinji Kobayashi, Ehime University, Japan", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Rikard Lovstrom, Swedish Medical Association, Sweden", "Ian McNicoll, Ocean Informatics, United Kingdom", "Jeroen Meintjens, Medisch Centrum Alkmaar, Netherlands", "Arturo Romero, SESCAM, Spain", "Soon Ghee Yap, Singapore Health Services Pte Ltd, Singapore">
	other_details = <
		["references"] = <"Clinical Guidelines on the Identification, Evaluation, and Treatment of Overweight and Obesity in Adults: The Evidence Report [Internet]. Bethesda (MD): National Heart, Lung, and Blood Institute; NIH Publication No. 98-4083, Sep 1998, [cited 2009 July 02]. Available from: http://www.nhlbi.nih.gov/guidelines/obesity/

About BMI for Children and Teens [Internet]. Atlanta (GA): Division of Nutrition, Physical Activity and Obesity, Centers for Disease Control and Prevention; 2009 Jan 27 [cited 2009 Jul 28 ]. Available from: http://www.cdc.gov/healthyweight/assessing/bmi/childrens_BMI/about_childrens_BMI.html

WHO Child Growth Standards: Length/height-for-age, weight-for-age, weight-for-length, weight-for-height and body mass index-for-age: Methods and development. [Internet] Geneva, Switzerland: WHO Multicentre Growth Reference Study Group, World Health Organization; 2006 [cited 2009 July 02].  Chapter 6, BMI-for-age standards. Available from: http://www.who.int/childgrowth/standards/Chap_6.pdf.

Obesity: Preventing and Managing the Global Epidemic: Report of a WHO Consultation [Internet]. Geneva, Switzerland: World Health Organisation; 2000 [cited 2009 Jul 28]. Available from: http://www.who.int/nutrition/publications/obesity/WHO_TRS_894/en/index.html

Tzamaloukas AH, Patron A, Malhotra D. Body Mass Index in Amputees. Journal of Parenteral and Enteral Nutrition [Internet]. 1994 [cited 2009 Jul 28]; 18 (4): 355. Available from: http://pen.sagepub.com/cgi/content/abstract/18/4/355  



">
		["MD5-CAM-1.0.1"] = <"43E7333B2B747AC6FBADE17ED6C293F1">
	>

definition
	OBSERVATION[at0000] matches {	-- Indice de massa corpórea
		data matches {
			HISTORY[at0001] matches {	-- history
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0002] occurrences matches {1..*} matches {	-- Qualquer evento
						data matches {
							ITEM_TREE[at0003] matches {	-- Single
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0004] matches {	-- Indice de massa corpórea
										value matches {
											C_DV_QUANTITY <
												property = <[openehr::349]>
												list = <
													["1"] = <
														units = <"kg/m2">
														magnitude = <|0.0..<1000.0|>
														precision = <|1|>
													>
													["2"] = <
														units = <"lb/in2">
														magnitude = <|0.0..<1000.0|>
														precision = <|1|>
													>
												>
											>
										}
									}
								}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_LIST[at0005] matches {	-- List
				items cardinality matches {0..*; ordered} matches {
					ELEMENT[at0006] occurrences matches {0..1} matches {	-- Método
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0007, 	-- Entrada automática
									at0008]	-- Entrada direta
								}
							}
						}
					}
					ELEMENT[at0010] occurrences matches {0..1} matches {	-- Fórmula
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0011] occurrences matches {0..1} matches {	-- Comentário
						value matches {
							DV_TEXT matches {*}
						}
					}
				}
			}
		}
	}


ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Body mass index">
					description = <"Calculated measurement which compares a person's weight and height.">
				>
				["at0001"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"Any timed recording of Body Mass Index.">
				>
				["at0003"] = <
					text = <"Single">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Body Mass Index">
					description = <"Index describing ratio of weight to height.">
				>
				["at0005"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0006"] = <
					text = <"Method">
					description = <"The method of entering the Body Mass Index.">
				>
				["at0007"] = <
					text = <"Automatic entry">
					description = <"Body Mass Index calculated and entered automatically without user intervention.">
				>
				["at0008"] = <
					text = <"Direct entry">
					description = <"Body Mass Index calculated and entered directly by user.">
				>
				["at0010"] = <
					text = <"Formula">
					description = <"Formula used to derive the Body Mass Index.">
				>
				["at0011"] = <
					text = <"Comment">
					description = <"Comment about the Body Mass Index measurement eg noting that the measurements used were adjusted weight/height.">
				>
			>
		>
		["nl"] = <
			items = <
				["at0000"] = <
					text = <"Body mass index">
					description = <"Berekende meting welke gewicht en lengte van een persoon vergelijkt.">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"Elke gebeurtenis">
					description = <"Opslag van iedere meting van de Body Mass Index">
				>
				["at0003"] = <
					text = <"*Single(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Body Mass Index">
					description = <"Index om ratio gewicht - lengte te beschrijven">
				>
				["at0005"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0006"] = <
					text = <"Methode">
					description = <"De methode om de Body Mass Index in te voeren.">
				>
				["at0007"] = <
					text = <"Automatische invoer">
					description = <"Body Mass Index is automatisch berekend en ingevoerd, zonder tussenkomst van gebruikers.">
				>
				["at0008"] = <
					text = <"Direkte invoer">
					description = <"Body Mass Index is berekend en ingevoerd door de gebruiker.">
				>
				["at0010"] = <
					text = <"Formule">
					description = <"De formule die gebruikt wordt om de Body Mass Index te berekenen">
				>
				["at0011"] = <
					text = <"Opmerking">
					description = <"Opmerking over de Body Mass Index meting, b.v. dat de metingen die gebruikt werden voor de berekening, aangepaste lengte/gewicht zijn.">
				>
			>
		>
		["pt-br"] = <
			items = <
				["at0000"] = <
					text = <"Indice de massa corpórea">
					description = <"IMC - medida que compara o peso de uma pessoa com a altura.">
				>
				["at0001"] = <
					text = <"history">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Qualquer evento">
					description = <"Gravação a qualquer momento do Índice de Massa Corpórea.">
				>
				["at0003"] = <
					text = <"Single">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Indice de massa corpórea">
					description = <"Índice que descreve a relação de peso com a altura.">
				>
				["at0005"] = <
					text = <"List">
					description = <"@ internal @">
				>
				["at0006"] = <
					text = <"Método">
					description = <"Método de entrada do IMC.">
				>
				["at0007"] = <
					text = <"Entrada automática">
					description = <"IMC registrado automaticamente, sem a intervenção do usuário.">
				>
				["at0008"] = <
					text = <"Entrada direta">
					description = <"IMC registrado diretamente pelo usuário.">
				>
				["at0010"] = <
					text = <"Fórmula">
					description = <"Fórmula usada para calcular o IMC (somente se for diferente de peso/altura^2).">
				>
				["at0011"] = <
					text = <"Comentário">
					description = <"Comentário sobre a medição, por exemplo, IMC observando que as medidas utilizadas foram ajustadas para peso / altura.">
				>
			>
		>
		["fa"] = <
			items = <
				["at0000"] = <
					text = <"شاخص توده بدن">
					description = <"اندازه گیری محاسبه شده ای که وزن و قد افراد را مقایسه می کند
">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"هر رویداد">
					description = <"هر گونه ثبت زمانی شاخص توده بدن">
				>
				["at0003"] = <
					text = <"*Single(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"شاخص توده بدن">
					description = <"شاخصی که نسبت وزن به قد را توصیف می کند">
				>
				["at0005"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0006"] = <
					text = <"روش">
					description = <"روش ثبت شاخص توده بدن">
				>
				["at0007"] = <
					text = <"ثبت خودکار">
					description = <" شاخص توده بدن بطور خودکار بدون مداخله کاربر محاسبه و ثبت می شود">
				>
				["at0008"] = <
					text = <"ورود مستقیم داده ها">
					description = <"شاخص توده بدن مستقیما توسط کاربر محاسبه و ثبت می شود">
				>
				["at0010"] = <
					text = <"فرمول">
					description = <"فرمول مورد استفاده برای استخراج شاخص توده بدن">
				>
				["at0011"] = <
					text = <"نظر">
					description = <"نظر در مورد اندازه گیری شاخص توده بدن به عنوان مثال ذکر اینکه در اندازه گیری های انجام شده از وزن و یا قد معادل استفاده شده است ">
				>
			>
		>
		["es-ar"] = <
			items = <
				["at0000"] = <
					text = <"Índice de masa corporal">
					description = <"Medición calculada que compara el peso y altura de un individuo">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"Cualquier evento">
					description = <"Cualquier registro en el tiempo del Índice de Masa Corporal">
				>
				["at0003"] = <
					text = <"*Single(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"Índice de Masa Corporal">
					description = <"Índice que describe el cociente entre peso y altura.">
				>
				["at0005"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0006"] = <
					text = <"Método">
					description = <"El método de registro del Índice de Masa Corporal.">
				>
				["at0007"] = <
					text = <"Registro automático">
					description = <"Índice de Masa Corporal calculado e ingresado automáticamente sin intervención del usuario.">
				>
				["at0008"] = <
					text = <"Entrada directa">
					description = <"Índice de Masa Corporal calculado e ingresado directamente por el usuario.">
				>
				["at0010"] = <
					text = <"Fórmula">
					description = <"Fórmula usada para calcular el Índice de Masa Corporal.">
				>
				["at0011"] = <
					text = <"Comentario">
					description = <"Comentario sobre la medición del Índice de Masa Corporal ej: informando que la medición registrada fue peso/altura ajustado. ">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"معامل كتلة الجسم">
					description = <"قياس حسابي يجمع بين وزن الشخص و طوله">
				>
				["at0001"] = <
					text = <"*history(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"إحدى الوقائع">
					description = <"قياس معامل كتلة الجسم في وقت معين">
				>
				["at0003"] = <
					text = <"*Single(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"معامل كتلة الجسم">
					description = <"معامل يصف النسبة بين الوزن و الطول">
				>
				["at0005"] = <
					text = <"*List(en)">
					description = <"*@ internal @(en)">
				>
				["at0006"] = <
					text = <"الطريقة">
					description = <"طريقة إدخال معامل كتلة الجسم">
				>
				["at0007"] = <
					text = <"إدخال تلقائي">
					description = <"يتم حساب و إدخال معامل كتلةالجسم تلقائيا بدون تدخل من المستخدِم">
				>
				["at0008"] = <
					text = <"إدخال مباشر">
					description = <"يتم حساب و إدخال كتلة الجسم مباشرة بواسطة المستخدم">
				>
				["at0010"] = <
					text = <"الصيغة">
					description = <"الصيغة المستخدمة لاشتقاق معامل كتلة الجسم">
				>
				["at0011"] = <
					text = <"تعليق">
					description = <"تعليق حول قياس معامل كتلة الجسم مثل ملاحظة أن القياسات المستخدمة هي قياسات مصححة للوزن و الطول">
				>
			>
		>
	>

```

