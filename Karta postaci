<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Karta Postaci RPG - Projekt X v1.1</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6; /* Jasnoszary tło */
            color: #1f2937; /* Ciemnoszary tekst */
        }
        .container-main {
            max-width: 900px; /* Szerszy kontener dla lepszego układu */
            background-color: #ffffff; /* Białe tło dla karty */
            border-radius: 0.75rem; /* rounded-xl */
            box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -2px rgba(0,0,0,0.05);
        }
        label {
            color: #4b5563; /* Ciemniejszy szary dla etykiet */
            font-weight: 500; /* Medium */
        }
        input[type="text"], input[type="number"], textarea, select {
            background-color: #f9fafb; /* Bardzo jasny szary dla pól */
            border-color: #d1d5db; /* Jasnoszary dla ramek */
            color: #1f2937;
            border-radius: 0.375rem; /* rounded-md */
        }
        input[type="text"]:focus, input[type="number"]:focus, textarea:focus, select:focus {
            border-color: #fbbf24; /* Bursztynowy-400 dla focusa */
            --tw-ring-color: #fbbf24;
            box-shadow: 0 0 0 1px #fbbf24;
        }
        input[readonly] {
            background-color: #e5e7eb; /* Szary-200 dla pól tylko do odczytu */
            color: #6b7280; /* Szary-500 */
        }
        .section {
            margin-bottom: 1.5rem; /* mb-6 */
            padding: 1.5rem; /* p-6 */
            background-color: #f9fafb; /* Szary-50 */
            border-radius: 0.5rem; /* rounded-lg */
            border: 1px solid #e5e7eb; /* border-gray-200 */
        }
        .section-title {
            color: #ca8a04; /* Ciemny bursztynowy/żółty-600 */
            border-bottom: 2px solid #fde68a; /* Jasny bursztynowy/żółty-200 */
            padding-bottom: 0.5rem; /* pb-2 */
            margin-bottom: 1rem; /* mb-4 */
            font-size: 1.25rem; /* text-xl */
            font-weight: 600; /* font-semibold */
        }
        .btn {
            font-weight: 600;
            padding: 0.625rem 1rem;
            border-radius: 0.375rem;
            transition: background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
            text-align: center;
        }
        .btn-primary { background-color: #f59e0b; color: #ffffff; } /* Amber-500 */
        .btn-primary:hover { background-color: #d97706; } /* Amber-600 */
        .btn-secondary { background-color: #3b82f6; color: #ffffff; } /* Blue-500 */
        .btn-secondary:hover { background-color: #2563eb; } /* Blue-600 */
        .btn-danger { background-color: #ef4444; color: #ffffff; } /* Red-500 */
        .btn-danger:hover { background-color: #dc2626; } /* Red-600 */
        
        .effective-stat-display { color: #16a34a; font-weight: bold; } /* Green-600 */
        .exp-bar-container {
            background-color: #e5e7eb; border-radius: 9999px; 
            height: 1rem; /* h-4 */ overflow: hidden; border: 1px solid #d1d5db; 
        }
        .exp-bar-fill {
            background-color: #34d399; /* Emerald-400 */ height: 100%;
            border-radius: 9999px; transition: width 0.3s ease-in-out;
        }
        .level-up-flash { animation: flash-animation 1.5s ease-out; }
        @keyframes flash-animation {
            0%, 100% { background-color: #f9fafb; } 
            50% { background-color: #a7f3d0; } /* Emerald-200 */
        }
        .dynamic-list-item {
            background-color: #ffffff; border: 1px solid #e5e7eb;
            padding: 0.75rem; margin-bottom: 0.5rem; border-radius: 0.375rem;
            display: flex; flex-direction: column; gap: 0.5rem;
        }
    </style>
</head>
<body class="p-4 md:p-8">
    <div class="container-main mx-auto p-4 sm:p-6 lg:p-8">
        <header class="mb-8 text-center">
            <h1 class="text-3xl sm:text-4xl font-bold text-amber-600">Karta Postaci - Projekt X</h1>
            <p class="text-gray-600 mt-2">Zarządzaj swoją postacią w nowym świecie!</p>
        </header>

        <form id="characterSheetForm">
            <section class="section">
                <h2 class="section-title">Podstawowe Informacje</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-x-6 gap-y-4">
                    <div>
                        <label for="charName" class="block text-sm mb-1">Imię Postaci:</label>
                        <input type="text" id="charName" name="charName" class="w-full p-2 border">
                    </div>
                    <div>
                        <label for="charConcept" class="block text-sm mb-1">Koncept Postaci:</label>
                        <input type="text" id="charConcept" name="charConcept" class="w-full p-2 border" placeholder="Np. Haker idealista, Były żołnierz">
                    </div>
                    <div>
                        <label for="charLevel" class="block text-sm mb-1">Poziom:</label>
                        <input type="number" id="charLevel" name="charLevel" value="1" min="1" class="w-full p-2 border" readonly>
                    </div>
                    <div>
                        <label for="charExpCurrent" class="block text-sm mb-1">Aktualne EXP:</label>
                        <input type="number" id="charExpCurrent" name="charExpCurrent" value="0" min="0" class="w-full p-2 border">
                    </div>
                    <div>
                        <label for="charExpNextLevel" class="block text-sm mb-1">EXP do Nast. Poziomu:</label>
                        <input type="number" id="charExpNextLevel" name="charExpNextLevel" value="1000" class="w-full p-2 border" readonly>
                    </div>
                    <div>
                        <label for="charAttrPoints" class="block text-sm mb-1">Nierozdane Pkt. Atrybutów:</label>
                        <input type="number" id="charAttrPoints" name="charAttrPoints" value="59" min="0" class="w-full p-2 border">
                    </div>
                    <div class="md:col-span-3 mt-2">
                        <label class="block text-sm mb-1 text-center">Postęp Doświadczenia:</label>
                        <div class="exp-bar-container w-full">
                            <div id="expProgressBar" class="exp-bar-fill" style="width: 0%;"></div>
                        </div>
                        <p id="expProgressText" class="text-xs text-center text-gray-500 mt-1">0 / 1000 EXP</p>
                    </div>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Atrybuty Główne</h2>
                <p class="text-xs text-gray-500 mb-3">Modyfikator: Bazowe 10 = 0; 11-12 = 0; 13-15 = +1; 16-18 = +2 itd. (oraz 7-9 = -1; 4-6 = -2; 1-3 = -3; 0 = -3). Max 18 przy tworzeniu.</p>
                <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-6 gap-4">
                    <div class="text-center">
                        <label for="attrStrBase" class="block text-sm mb-1">Siła (STR)</label>
                        <input type="number" id="attrStrBase" name="attrStrBase" value="0" min="0" max="18" class="w-full p-2 border text-center char-attribute">
                        <p class="text-xs mt-1">Mod: <span id="attrStrMod" class="effective-stat-display">0</span></p>
                    </div>
                    <div class="text-center">
                        <label for="attrDexBase" class="block text-sm mb-1">Zręczność (DEX)</label>
                        <input type="number" id="attrDexBase" name="attrDexBase" value="0" min="0" max="18" class="w-full p-2 border text-center char-attribute">
                        <p class="text-xs mt-1">Mod: <span id="attrDexMod" class="effective-stat-display">0</span></p>
                    </div>
                    <div class="text-center">
                        <label for="attrConBase" class="block text-sm mb-1">Kondycja (CON)</label>
                        <input type="number" id="attrConBase" name="attrConBase" value="0" min="0" max="18" class="w-full p-2 border text-center char-attribute">
                        <p class="text-xs mt-1">Mod: <span id="attrConMod" class="effective-stat-display">0</span></p>
                    </div>
                    <div class="text-center">
                        <label for="attrIntBase" class="block text-sm mb-1">Inteligencja (INT)</label>
                        <input type="number" id="attrIntBase" name="attrIntBase" value="0" min="0" max="18" class="w-full p-2 border text-center char-attribute">
                        <p class="text-xs mt-1">Mod: <span id="attrIntMod" class="effective-stat-display">0</span></p>
                    </div>
                    <div class="text-center">
                        <label for="attrSprtBase" class="block text-sm mb-1">Spryt (SPRT)</label>
                        <input type="number" id="attrSprtBase" name="attrSprtBase" value="0" min="0" max="18" class="w-full p-2 border text-center char-attribute">
                        <p class="text-xs mt-1">Mod: <span id="attrSprtMod" class="effective-stat-display">0</span></p>
                    </div>
                    <div class="text-center">
                        <label for="attrChaBase" class="block text-sm mb-1">Charyzma (CHA)</label>
                        <input type="number" id="attrChaBase" name="attrChaBase" value="0" min="0" max="18" class="w-full p-2 border text-center char-attribute">
                        <p class="text-xs mt-1">Mod: <span id="attrChaMod" class="effective-stat-display">0</span></p>
                    </div>
                </div>
                 <p class="text-xs text-gray-500 mt-3">Przy tworzeniu postaci (Poziom 1): 59 punktów do rozdania (start od 0 dla każdego atrybutu, max 18). Rozwój w grze: +2 punkty na poziom, koszt progresywny.</p>
            </section>

            <section class="section">
                <h2 class="section-title">Statystyki Bojowe</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-x-6 gap-y-4">
                    <div>
                        <label for="hpCurrent" class="block text-sm mb-1">Aktualne HP:</label>
                        <input type="number" id="hpCurrent" name="hpCurrent" value="10" class="w-full p-2 border">
                    </div>
                    <div>
                        <label for="hpMax" class="block text-sm mb-1">Maksymalne HP:</label>
                        <input type="number" id="hpMax" name="hpMax" value="10" class="w-full p-2 border">
                    </div>
                    <div>
                        <label for="armorClass" class="block text-sm mb-1">Klasa Pancerza (AC):</label>
                        <input type="number" id="armorClass" name="armorClass" value="10" class="w-full p-2 border">
                    </div>
                     <div>
                        <label for="attackBonus" class="block text-sm mb-1">Premia do Ataku (ogólna):</label>
                        <input type="number" id="attackBonus" name="attackBonus" value="0" class="w-full p-2 border">
                    </div>
                    <div>
                        <label for="defenseBonus" class="block text-sm mb-1">Premia do Obrony (ogólna):</label>
                        <input type="number" id="defenseBonus" name="defenseBonus" value="0" class="w-full p-2 border">
                    </div>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Umiejętności</h2>
                <div id="skillsContainer">
                    </div>
                <button type="button" id="addSkillBtn" class="mt-4 btn btn-secondary text-sm">Dodaj Umiejętność</button>
            </section>

            <section class="section">
                <h2 class="section-title">"Techno-magia" (Urządzenia Aktywne/Posiadane)</h2>
                <div id="devicesContainer">
                    </div>
                <button type="button" id="addDeviceBtn" class="mt-4 btn btn-secondary text-sm">Dodaj Urządzenie</button>
            </section>

            <section class="section">
                <h2 class="section-title">Ekwipunek (Plecak / Inne)</h2>
                <textarea id="inventoryItems" name="inventoryItems" rows="6" class="w-full p-2 border" placeholder="Wpisz tutaj posiadane przedmioty, np. Latarka, Zestaw narzędzi, Gotówka: 500 PLN..."></textarea>
            </section>

            <section class="section">
                <h2 class="section-title">Notatki Fabularne</h2>
                <textarea id="notes" name="notes" rows="6" class="w-full p-2 border" placeholder="Wpisz tutaj notatki dotyczące przygody, ważnych informacji, celów postaci itp."></textarea>
            </section>
            
            <section class="section">
                <h2 class="section-title">Poznane Postacie (NPC)</h2>
                <div id="npcEntriesContainer">
                    </div>
                <button type="button" id="addNpcBtn" class="mt-4 btn btn-secondary text-sm">Dodaj NPC</button>
            </section>

        </form>

        <section class="mt-8 p-6 bg-gray-100 rounded-lg shadow-inner">
            <h2 class="section-title text-gray-700">Zapisz / Wczytaj Postać</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
                <button type="button" id="exportDataBtn" class="w-full btn btn-primary">Eksportuj Dane Postaci</button>
                <button type="button" id="importDataBtn" class="w-full btn btn-secondary">Importuj Dane Postaci</button>
            </div>
            <textarea id="exportImportArea" rows="6" class="w-full p-2 border text-sm" placeholder="Tutaj pojawią się dane do skopiowania (eksport) lub tutaj wklej dane do zaimportowania..."></textarea>
            <p id="statusMessage" class="text-sm mt-2 text-amber-700"></p>
        </section>

        <footer class="mt-12 text-center text-sm text-gray-500">
            <p>&copy; Stworzone dla Projektu X RPG</p>
        </footer>
    </div>

    <script>
        // --- ELEMENTY DOM ---
        const charNameInput = document.getElementById('charName');
        const charConceptInput = document.getElementById('charConcept');
        const charLevelInput = document.getElementById('charLevel');
        const charExpCurrentInput = document.getElementById('charExpCurrent');
        const charExpNextLevelInput = document.getElementById('charExpNextLevel');
        const charAttrPointsInput = document.getElementById('charAttrPoints');
        const expProgressBar = document.getElementById('expProgressBar');
        const expProgressText = document.getElementById('expProgressText');

        const attrInputs = {
            Str: document.getElementById('attrStrBase'), Dex: document.getElementById('attrDexBase'),
            Con: document.getElementById('attrConBase'), Int: document.getElementById('attrIntBase'),
            Sprt: document.getElementById('attrSprtBase'), Cha: document.getElementById('attrChaBase')
        };
        const attrMods = {
            Str: document.getElementById('attrStrMod'), Dex: document.getElementById('attrDexMod'),
            Con: document.getElementById('attrConMod'), Int: document.getElementById('attrIntMod'),
            Sprt: document.getElementById('attrSprtMod'), Cha: document.getElementById('attrChaMod')
        };

        const hpCurrentInput = document.getElementById('hpCurrent');
        const hpMaxInput = document.getElementById('hpMax');
        const armorClassInput = document.getElementById('armorClass');
        const attackBonusInput = document.getElementById('attackBonus');
        const defenseBonusInput = document.getElementById('defenseBonus');

        const skillsContainer = document.getElementById('skillsContainer');
        const addSkillBtn = document.getElementById('addSkillBtn');
        const devicesContainer = document.getElementById('devicesContainer');
        const addDeviceBtn = document.getElementById('addDeviceBtn');
        const inventoryItemsTextarea = document.getElementById('inventoryItems');
        const notesTextarea = document.getElementById('notes');
        
        const npcEntriesContainer = document.getElementById('npcEntriesContainer');
        const addNpcBtn = document.getElementById('addNpcBtn');
        let npcCounter = 0;

        const exportDataBtn = document.getElementById('exportDataBtn');
        const importDataBtn = document.getElementById('importDataBtn');
        const exportImportArea = document.getElementById('exportImportArea');
        const statusMessage = document.getElementById('statusMessage');

        // --- STAŁE SYSTEMOWE ---
        const INITIAL_ATTRIBUTE_POOL = 59;
        const MAX_ATTRIBUTE_AT_CREATION = 18;
        const BASE_EXP_FOR_LEVEL_2 = 1000;
        const EXP_MULTIPLIER = 1.5;
        const ATTRIBUTE_POINTS_PER_LEVEL = 2;

        // --- FUNKCJE PODSTAWOWE ---
        function calculateAttributeModifier(value) {
            value = parseInt(value) || 0; // Upewnij się, że to liczba
            if (value <= 0) return -3;
            if (value >= 1 && value <= 3) return -3;
            if (value >= 4 && value <= 6) return -2;
            if (value >= 7 && value <= 9) return -1;
            if (value >= 10 && value <= 12) return 0;
            if (value >= 13 && value <= 15) return +1;
            if (value >= 16 && value <= 18) return +2;
            
            let mod = 2; // Start from +2 for 18
            for (let i = 19; i <= value; i++) { // Check each point above 18
                if ((i - 18) % 3 === 1 && i > 18) { // Increment modifier for every 3 points starting from 19 (19, 22, 25...)
                    mod++;
                }
            }
            return mod;
        }

        function updateAllAttributeModifiers() {
            for (const key in attrInputs) {
                const value = parseInt(attrInputs[key].value) || 0;
                attrMods[key].textContent = calculateAttributeModifier(value);
            }
        }

        function updateExpDisplay() {
            const currentExp = parseInt(charExpCurrentInput.value) || 0;
            const expToNext = parseInt(charExpNextLevelInput.value) || BASE_EXP_FOR_LEVEL_2;
            let progressPercent = 0;
            if (expToNext > 0) {
                progressPercent = Math.min((currentExp / expToNext) * 100, 100);
            }
            expProgressBar.style.width = `${progressPercent}%`;
            expProgressText.textContent = `${currentExp} / ${expToNext} EXP`;
        }

        function checkLevelUp() {
            let currentExp = parseInt(charExpCurrentInput.value) || 0;
            let expToNext = parseInt(charExpNextLevelInput.value) || BASE_EXP_FOR_LEVEL_2;
            let level = parseInt(charLevelInput.value) || 1;
            let attrPoints = parseInt(charAttrPointsInput.value) || 0; // Używamy tej puli
            let leveledUp = false;

            while (currentExp >= expToNext) {
                level++;
                currentExp -= expToNext;
                expToNext = Math.floor(expToNext * EXP_MULTIPLIER);
                attrPoints += ATTRIBUTE_POINTS_PER_LEVEL;
                leveledUp = true;
                
                charLevelInput.classList.add('level-up-flash');
                statusMessage.textContent = `Gratulacje! Osiągnięto Poziom ${level}! Otrzymujesz ${ATTRIBUTE_POINTS_PER_LEVEL} pkt. atrybutów.`;
                setTimeout(() => { 
                    statusMessage.textContent = ''; 
                    charLevelInput.classList.remove('level-up-flash');
                }, 5000);
            }

            if (leveledUp) {
                charLevelInput.value = level;
                charExpCurrentInput.value = currentExp;
                charExpNextLevelInput.value = expToNext;
                charAttrPointsInput.value = attrPoints; // Aktualizujemy pulę punktów
            }
            updateExpDisplay();
        }
        
        // Funkcja do obsługi alokacji punktów atrybutów przy tworzeniu postaci (Poziom 1)
        function handleInitialAttributeAllocation() {
            if (parseInt(charLevelInput.value) !== 1) {
                // Ta logika dotyczy tylko tworzenia postaci na poziomie 1
                // Dla wyższych poziomów rozwój atrybutów jest obsługiwany przez punkty z `charAttrPointsInput` i progresywny koszt
                updateAllAttributeModifiers(); // Zawsze aktualizuj modyfikatory
                return;
            }

            let totalPointsAllocated = 0;
            Object.values(attrInputs).forEach(input => {
                let val = parseInt(input.value) || 0;
                // Walidacja wartości wprowadzanej do pola atrybutu
                if (val < 0) {
                    input.value = 0;
                    val = 0;
                } else if (val > MAX_ATTRIBUTE_AT_CREATION) {
                    input.value = MAX_ATTRIBUTE_AT_CREATION;
                    val = MAX_ATTRIBUTE_AT_CREATION;
                    statusMessage.textContent = `Maks. wartość atrybutu przy tworzeniu to ${MAX_ATTRIBUTE_AT_CREATION}.`;
                    setTimeout(() => statusMessage.textContent = '', 3000);
                }
                totalPointsAllocated += val;
            });

            if (totalPointsAllocated > INITIAL_ATTRIBUTE_POOL) {
                // Jeśli suma przekracza pulę, trzeba cofnąć ostatnią zmianę lub ją ograniczyć
                // Ta część wymagałaby śledzenia poprzedniej wartości lub bardziej złożonej logiki
                // Na razie, po prostu poinformujemy użytkownika i zaktualizujemy pulę, która może spaść poniżej 0
                statusMessage.textContent = `Przekroczono pulę ${INITIAL_ATTRIBUTE_POOL} punktów! Dostosuj wartości.`;
                 setTimeout(() => statusMessage.textContent = '', 3000);
                 // Proste cofnięcie ostatniej zmiany jest trudne bez śledzenia stanu `focus`/`blur` i `oldValue`
                 // Zamiast tego, pozwalamy na chwilowe przekroczenie, ale pole nierozdanych punktów to pokaże
            }
            
            charAttrPointsInput.value = Math.max(0, INITIAL_ATTRIBUTE_POOL - totalPointsAllocated);
            updateAllAttributeModifiers();
        }


        // --- OBSŁUGA DYNAMICZNYCH LIST (UMIEJĘTNOŚCI, URZĄDZEŃ, NPC) ---
        function createDynamicListItem(container, type, data = {}) {
            const itemDiv = document.createElement('div');
            itemDiv.classList.add('dynamic-list-item');
            let content = '';

            if (type === 'skill') {
                content = `
                    <input type="text" class="w-full p-1 border text-sm skill-name" placeholder="Nazwa Umiejętności" value="${data.name || ''}">
                    <div class="grid grid-cols-2 gap-2">
                        <input type="number" class="w-full p-1 border text-sm skill-level" placeholder="Poziom" min="1" value="${data.level || '1'}">
                        <input type="text" class="w-full p-1 border text-sm skill-attr" placeholder="Pow. Atrybut (np. SPRT)" value="${data.attr || ''}">
                    </div>
                    <textarea class="w-full p-1 border text-xs skill-effect" rows="2" placeholder="Krótki opis/efekt">${data.effect || ''}</textarea>
                `;
            } else if (type === 'device') {
                content = `
                    <input type="text" class="w-full p-1 border text-sm device-name" placeholder="Nazwa Urządzenia" value="${data.name || ''}">
                    <textarea class="w-full p-1 border text-xs device-effect" rows="2" placeholder="Opis/Efekt, Wymagania">${data.effect || ''}</textarea>
                `;
            } else if (type === 'npc') {
                 npcCounter++;
                 itemDiv.setAttribute('data-npc-id', npcCounter);
                 content = `
                    <input type="text" id="npcName_${npcCounter}" class="w-full p-1 border text-sm npc-name" placeholder="Imię NPC" value="${data.name || ''}">
                    <input type="text" id="npcRelation_${npcCounter}" class="w-full p-1 border text-sm npc-relation" placeholder="Stosunek do postaci" value="${data.relation || ''}">
                    <textarea id="npcBio_${npcCounter}" rows="2" class="w-full p-1 border text-xs npc-bio" placeholder="Krótkie bio">${data.bio || ''}</textarea>
                    <textarea id="npcPlot_${npcCounter}" rows="2" class="w-full p-1 border text-xs npc-plot" placeholder="Związek z fabułą">${data.plot || ''}</textarea>
                 `;
            }
            
            const removeBtn = document.createElement('button');
            removeBtn.type = 'button';
            removeBtn.classList.add('btn', 'btn-danger', 'text-xs', 'py-1', 'self-end');
            removeBtn.textContent = 'Usuń';
            removeBtn.onclick = () => itemDiv.remove();

            itemDiv.innerHTML = content;
            itemDiv.appendChild(removeBtn);
            container.appendChild(itemDiv);
        }
        
        addSkillBtn.addEventListener('click', () => createDynamicListItem(skillsContainer, 'skill'));
        addDeviceBtn.addEventListener('click', () => createDynamicListItem(devicesContainer, 'device'));
        addNpcBtn.addEventListener('click', () => createDynamicListItem(npcEntriesContainer, 'npc'));


        // --- NASŁUCHIWACZE ZDARZEŃ ---
        Object.values(attrInputs).forEach(input => {
            // Używamy 'input' dla natychmiastowej reakcji, 'change' po utracie focusa
            input.addEventListener('input', handleInitialAttributeAllocation); 
        });
        charExpCurrentInput.addEventListener('input', checkLevelUp);

        // --- ZAPIS/WCZYTANIE DANYCH ---
        const formElementsToSave = [
            'charName', 'charConcept', 'charLevel', 'charExpCurrent', 'charExpNextLevel', 'charAttrPoints',
            'attrStrBase', 'attrDexBase', 'attrConBase', 'attrIntBase', 'attrSprtBase', 'attrChaBase',
            'hpCurrent', 'hpMax', 'armorClass', 'attackBonus', 'defenseBonus',
            'inventoryItems', 'notes'
        ];

        exportDataBtn.addEventListener('click', () => {
            const characterData = {};
            formElementsToSave.forEach(id => {
                const element = document.getElementById(id);
                if (element) characterData[id] = element.value;
            });

            characterData.skills = [];
            skillsContainer.querySelectorAll('.dynamic-list-item').forEach(item => {
                characterData.skills.push({
                    name: item.querySelector('.skill-name').value,
                    level: item.querySelector('.skill-level').value,
                    attr: item.querySelector('.skill-attr').value,
                    effect: item.querySelector('.skill-effect').value
                });
            });
            
            characterData.devices = [];
            devicesContainer.querySelectorAll('.dynamic-list-item').forEach(item => {
                characterData.devices.push({
                    name: item.querySelector('.device-name').value,
                    effect: item.querySelector('.device-effect').value
                });
            });

            characterData.npcs = [];
            npcEntriesContainer.querySelectorAll('.dynamic-list-item').forEach(item => {
                characterData.npcs.push({
                    name: item.querySelector('.npc-name').value,
                    relation: item.querySelector('.npc-relation').value,
                    bio: item.querySelector('.npc-bio').value,
                    plot: item.querySelector('.npc-plot').value
                });
            });

            const dataString = JSON.stringify(characterData);
            exportImportArea.value = dataString;
            statusMessage.textContent = 'Dane gotowe do skopiowania!';
            try {
                navigator.clipboard.writeText(dataString)
                .then(() => { statusMessage.textContent = 'Dane skopiowane do schowka!'; })
                .catch(err => { /* Fallback jeśli schowek zawiedzie */ });
            } catch (e) { /* Starsze przeglądarki */ }
        });

        importDataBtn.addEventListener('click', () => {
            const dataString = exportImportArea.value.trim();
            if (!dataString) {
                statusMessage.textContent = 'Pole danych jest puste.';
                return;
            }
            try {
                const characterData = JSON.parse(dataString);
                formElementsToSave.forEach(id => {
                    const element = document.getElementById(id);
                    if (element && characterData[id] !== undefined) {
                        element.value = characterData[id];
                    }
                });

                skillsContainer.innerHTML = '';
                if (characterData.skills) {
                    characterData.skills.forEach(skillData => createDynamicListItem(skillsContainer, 'skill', skillData));
                }
                devicesContainer.innerHTML = '';
                if (characterData.devices) {
                    characterData.devices.forEach(deviceData => createDynamicListItem(devicesContainer, 'device', deviceData));
                }
                npcEntriesContainer.innerHTML = '';
                npcCounter = 0; 
                if (characterData.npcs) {
                    characterData.npcs.forEach(npcData => createDynamicListItem(npcEntriesContainer, 'npc', npcData));
                }
                
                // Po załadowaniu danych, jeśli postać jest na poziomie 1, przelicz pulę punktów atrybutów
                if (parseInt(charLevelInput.value) === 1) {
                    handleInitialAttributeAllocation(); // To zaktualizuje pole charAttrPointsInput
                }


                updateAllAttributeModifiers();
                updateExpDisplay();
                checkLevelUp(); 
                statusMessage.textContent = 'Dane postaci zaimportowane!';
                exportImportArea.value = '';
            } catch (error) {
                statusMessage.textContent = 'Błąd importu. Sprawdź format danych.';
                console.error("Import error:", error);
            }
        });

        // Inicjalizacja przy ładowaniu strony
        // Ustawienie początkowej wartości dla nierozdanych punktów przy tworzeniu nowej postaci
        if (!charNameInput.value) { // Prosty warunek na "nową postać" - można ulepszyć
             charAttrPointsInput.value = INITIAL_ATTRIBUTE_POOL;
             Object.values(attrInputs).forEach(input => input.value = 0); // Reset atrybutów do 0
        }
        updateAllAttributeModifiers();
        updateExpDisplay();
        checkLevelUp(); 
        // Po załadowaniu strony, jeśli jest to nowa postać (Poziom 1), zaktualizuj pulę punktów
        if (parseInt(charLevelInput.value) === 1) {
            handleInitialAttributeAllocation();
        }
    </script>
</body>
</html>


