<!DOCTYPE html>
<html lang="en" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Food and Drug Administration, Government of Maharashtra</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        govblue: {
                            700: '#1d4ed8',
                            800: '#1e40af',
                            900: '#172554'
                        },
                        govsaffron: {
                            600: '#ea580c',
                            700: '#c2410c'
                        }
                    }
                }
            }
        }
    </script>
    <!-- FontAwesome for official iconography -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Chart.js for Officer Dashboard analytics -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body class="h-full bg-slate-100 text-slate-800 font-sans flex flex-col justify-between selection:bg-blue-600 selection:text-white">

    <!-- TOP GOVERNMENT STRIP -->
    <header class="bg-govblue-900 text-white text-xs border-b border-blue-900">
        <div class="max-w-7xl mx-auto px-3 py-1 flex flex-col sm:flex-row justify-between items-center gap-1">
            <div class="flex items-center gap-2">
                <span class="inline-block w-2 h-2 rounded-full bg-amber-400"></span>
                <span class="tracking-wide">Government of Maharashtra | Medical Education and Drugs Department[cite: 1]</span>
            </div>
            <div class="flex items-center gap-4 text-slate-200">
                <span><i class="fa-solid fa-phone mr-1 text-amber-400"></i> Helpline: 1800-222-365</span>
                <span>|</span>
                <span class="bg-amber-500/20 text-amber-300 px-2 py-0.5 rounded text-[10px] font-semibold">Demonstration Prototype</span>
                <span>|</span>
                <button onclick="router.navigateTo('/officer-dashboard')" class="text-amber-300 hover:text-white font-medium transition-colors">
                    <i class="fa-solid fa-user-shield mr-1"></i> Officer Portal
                </button>
            </div>
        </div>
    </header>

    <!-- OFFICIAL GOVT BRANDING HEADER WITH MAHARASHTRA STATE EMBLEM -->
    <div class="bg-white border-b border-slate-300 shadow-xs">
        <div class="max-w-7xl mx-auto px-3 py-3 flex flex-col sm:flex-row items-center justify-between gap-4">
            <a href="#/" onclick="router.navigateTo('/')" class="flex items-center gap-3">
                <!-- Actual Maharashtra Government State Emblem (Maharashtra Government Seal) -->
                <div class="w-14 h-14 bg-white rounded flex items-center justify-center p-1 flex-shrink-0">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/2/26/Seal_of_Maharashtra.svg" alt="Government of Maharashtra Emblem" class="w-full h-full object-contain">
                </div>
                <div>
                    <h1 class="text-lg font-bold text-govblue-900 leading-tight">Food and Drug Administration, Maharashtra State</h1>
                    <p class="text-xs text-slate-600 font-medium">Medical Education and Drugs Department, Government of Maharashtra[cite: 1]</p>
                </div>
            </a>
            <div class="flex items-center gap-3 text-right">
                <div class="hidden md:block text-xs text-slate-600">
                    <p class="font-bold text-slate-800">"Your Concern. Our Responsibility."[cite: 1]</p>
                    <p class="text-[11px] text-slate-500">State Principal Regulatory Authority[cite: 1]</p>
                </div>
            </div>
        </div>
    </div>

    <!-- MAIN FORMAL NAVIGATION BAR -->
    <nav class="bg-govblue-800 text-white sticky top-0 z-40 shadow-md">
        <div class="max-w-7xl mx-auto px-3 flex items-center justify-between">
            <div class="hidden lg:flex items-center text-xs font-medium divide-x divide-blue-700">
                <a href="#/" onclick="router.navigateTo('/')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/">Home</a>
                <a href="#/services" onclick="router.navigateTo('/services')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/services">Services</a>
                <a href="#/complaints" onclick="router.navigateTo('/complaints')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/complaints">Grievances</a>
                <a href="#/alerts" onclick="router.navigateTo('/alerts')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/alerts">Safety Alerts</a>
                <a href="#/licences" onclick="router.navigateTo('/licences')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/licences">Licences</a>
                <a href="#/notices" onclick="router.navigateTo('/notices')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/notices">Notices</a>
                <a href="#/directory" onclick="router.navigateTo('/directory')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/directory">Directory</a>
                <a href="#/track-complaint" onclick="router.navigateTo('/track-complaint')" class="nav-link px-4 py-2.5 hover:bg-govblue-900 transition-colors" data-route="/track-complaint">Track Complaint</a>
            </div>

            <div class="flex items-center gap-2 py-1.5 w-full lg:w-auto justify-between lg:justify-end">
                <button onclick="openAiAssistantModal()" class="bg-amber-500 hover:bg-amber-600 text-slate-900 px-3 py-1.5 rounded text-xs font-bold shadow-xs transition-colors flex items-center gap-1.5">
                    <i class="fa-solid fa-robot"></i>
                    <span>FDA Sahayak (AI Assistant)</span>
                </button>
                <button onclick="toggleMobileMenu()" class="lg:hidden text-white p-1 rounded hover:bg-blue-900">
                    <i class="fa-solid fa-bars text-lg"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div id="mobile-menu" class="hidden lg:hidden border-t border-blue-700 bg-govblue-900 px-4 py-2 space-y-1 text-xs">
            <a href="#/" onclick="router.navigateTo('/'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Home</a>
            <a href="#/services" onclick="router.navigateTo('/services'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Services</a>
            <a href="#/complaints" onclick="router.navigateTo('/complaints'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Grievances</a>
            <a href="#/alerts" onclick="router.navigateTo('/alerts'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Safety Alerts</a>
            <a href="#/licences" onclick="router.navigateTo('/licences'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Licences</a>
            <a href="#/notices" onclick="router.navigateTo('/notices'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Notices</a>
            <a href="#/directory" onclick="router.navigateTo('/directory'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Directory</a>
            <a href="#/track-complaint" onclick="router.navigateTo('/track-complaint'); toggleMobileMenu();" class="block py-1.5 hover:text-amber-300">Track Complaint</a>
            <a href="#/officer-dashboard" onclick="router.navigateTo('/officer-dashboard'); toggleMobileMenu();" class="block py-1.5 text-amber-400 font-bold">Officer Portal</a>
        </div>
    </nav>

    <!-- MAIN APP CONTAINER -->
    <main id="app-container" class="flex-grow">
        <!-- Dynamic content injected here by router -->
    </main>

    <!-- FLOATING AI ASSISTANT BUTTON -->
    <div class="fixed bottom-4 right-4 z-50">
        <button onclick="openAiAssistantModal()" class="bg-govblue-800 hover:bg-govblue-900 text-white w-12 h-12 rounded-full shadow-lg flex items-center justify-center text-lg transition-all border-2 border-amber-400">
            <i class="fa-solid fa-robot text-amber-300"></i>
        </button>
    </div>

    <!-- AI SAHAYAK MODAL / CHAT INTERFACE -->
    <div id="ai-assistant-modal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-xs z-50 hidden flex items-center justify-center p-3">
        <div class="bg-white rounded shadow-xl w-full max-w-md overflow-hidden border border-slate-300 flex flex-col max-h-[85vh]">
            <div class="bg-govblue-900 text-white px-4 py-3 flex items-center justify-between border-b border-blue-900">
                <div class="flex items-center gap-2">
                    <div class="w-7 h-7 rounded bg-amber-500 flex items-center justify-center text-slate-900 font-bold text-xs">
                        <i class="fa-solid fa-robot"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-xs">FDA Sahayak — AI Citizen Assistant</h3>
                        <p class="text-[10px] text-slate-300">Verified FDA Data Context</p>
                    </div>
                </div>
                <button onclick="closeAiAssistantModal()" class="text-slate-300 hover:text-white">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <div id="ai-chat-messages" class="p-3 overflow-y-auto flex-grow space-y-3 bg-slate-50 text-xs">
                <div class="flex items-start gap-2">
                    <div class="w-6 h-6 rounded bg-govblue-900 text-amber-400 flex items-center justify-center flex-shrink-0 font-bold text-[10px]">AI</div>
                    <div class="bg-white p-2.5 rounded border border-slate-200 text-slate-700 max-w-[85%]">
                        <p class="font-medium text-slate-900 mb-1">Namaste. I am FDA Sahayak[cite: 1].</p>
                        <p>I can assist you with Maharashtra FDA services, official portals, safety alerts, and grievance procedures based strictly on official records[cite: 1].</p>
                    </div>
                </div>
            </div>

            <div class="px-3 py-2 bg-slate-100 border-t border-slate-200 flex gap-1.5 overflow-x-auto text-[11px] whitespace-nowrap">
                <button onclick="sendQuickPrompt('Where can I register a complaint?')" class="bg-white hover:bg-amber-50 text-slate-700 px-2.5 py-1 rounded border border-slate-300">Register complaint</button>
                <button onclick="sendQuickPrompt('Where can I apply for a food licence?')" class="bg-white hover:bg-amber-50 text-slate-700 px-2.5 py-1 rounded border border-slate-300">Food licence</button>
                <button onclick="sendQuickPrompt('What are the latest safety alerts?')" class="bg-white hover:bg-amber-50 text-slate-700 px-2.5 py-1 rounded border border-slate-300">Safety alerts</button>
            </div>

            <div class="p-2.5 bg-white border-t border-slate-200 flex items-center gap-2">
                <input type="text" id="ai-chat-input" placeholder="Ask about services, licences or alerts..." class="flex-grow px-3 py-1.5 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700" onkeydown="if(event.key==='Enter') submitAiChat()">
                <button onclick="submitAiChat()" class="bg-govblue-800 hover:bg-govblue-900 text-white px-3 py-1.5 rounded font-medium text-xs">
                    <i class="fa-solid fa-paper-plane"></i>
                </button>
            </div>
        </div>
    </div>

    <!-- OFFICIAL FOOTER -->
    <footer class="bg-govblue-900 text-slate-300 border-t border-blue-900 text-xs">
        <div class="max-w-7xl mx-auto px-3 py-8 grid grid-cols-1 md:grid-cols-4 gap-6">
            <div class="space-y-2">
                <h4 class="text-white font-bold text-xs uppercase tracking-wider border-b border-blue-800 pb-1">About FDA Maharashtra</h4>
                <p class="text-[11px] text-slate-300 leading-relaxed">
                    Food and Drug Administration, Government of Maharashtra, is the state principal regulatory authority dedicated to ensuring safety, quality, and compliance of food, drugs, and cosmetics[cite: 1].
                </p>
                <p class="text-[11px] text-amber-400 font-semibold">"Your Concern. Our Responsibility."[cite: 1]</p>
            </div>
            <div>
                <h4 class="text-white font-bold text-xs uppercase tracking-wider border-b border-blue-800 pb-1 mb-2">Official Portals[cite: 1]</h4>
                <ul class="space-y-1.5 text-[11px]">
                    <li><a href="http://foscos.fassai.gov.in/" target="_blank" class="hover:text-amber-300 flex items-center gap-1"><i class="fa-solid fa-external-link-alt text-[9px] text-amber-400"></i> FosCoS FSSAI Portal[cite: 1]</a></li>
                    <li><a href="https://fdamfg.maharashtra.gov.in/" target="_blank" class="hover:text-amber-300 flex items-center gap-1"><i class="fa-solid fa-external-link-alt text-[9px] text-amber-400"></i> FDA Drug Licenses (XLNIndia)[cite: 1]</a></li>
                    <li><a href="https://fdawhogmp.maharashtra.gov.in/" target="_blank" class="hover:text-amber-300 flex items-center gap-1"><i class="fa-solid fa-external-link-alt text-[9px] text-amber-400"></i> WHO-GMP Certificate Portal[cite: 1]</a></li>
                    <li><a href="https://festivals.mahafda.in/" target="_blank" class="hover:text-amber-300 flex items-center gap-1"><i class="fa-solid fa-external-link-alt text-[9px] text-amber-400"></i> Festival Community Food[cite: 1]</a></li>
                    <li><a href="https://complaints.mahafda.in/" target="_blank" class="hover:text-amber-300 flex items-center gap-1"><i class="fa-solid fa-external-link-alt text-[9px] text-amber-400"></i> Online Grievance Portal[cite: 1]</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-white font-bold text-xs uppercase tracking-wider border-b border-blue-800 pb-1 mb-2">Important Links[cite: 1]</h4>
                <ul class="space-y-1.5 text-[11px]">
                    <li><a href="https://www.maharashtra.gov.in/" target="_blank" class="hover:text-amber-300">Government of Maharashtra[cite: 1]</a></li>
                    <li><a href="https://medical.maharashtra.gov.in/" target="_blank" class="hover:text-amber-300">Medical Education & Drugs Dept.[cite: 1]</a></li>
                    <li><a href="https://fssai.gov.in/" target="_blank" class="hover:text-amber-300">FSSAI Central[cite: 1]</a></li>
                    <li><a href="https://cdsco.gov.in/" target="_blank" class="hover:text-amber-300">CDSCO India[cite: 1]</a></li>
                    <li><a href="https://aaplesarkar.mahaonline.gov.in/" target="_blank" class="hover:text-amber-300">Aaple Sarkar Portal[cite: 1]</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-white font-bold text-xs uppercase tracking-wider border-b border-blue-800 pb-1 mb-2">Headquarters</h4>
                <p class="text-[11px] text-slate-300 leading-relaxed mb-2">
                    Food and Drug Administration, Maharashtra State, Survey No. 341, Bandra-Kurla Complex, Mumbai, Maharashtra.
                </p>
                <div class="text-[11px] text-slate-300 space-y-1">
                    <p><i class="fa-solid fa-envelope mr-1 text-amber-400"></i> support.mahafd@gov.in</p>
                    <p><i class="fa-solid fa-phone mr-1 text-amber-400"></i> 022-26592365</p>
                </div>
            </div>
        </div>
        <div class="border-t border-blue-900 bg-blue-950 py-3 text-center text-[11px] text-slate-400">
            <div class="max-w-7xl mx-auto px-3 flex flex-col sm:flex-row justify-between items-center gap-1">
                <p>© 2026 Food and Drug Administration, Government of Maharashtra. All Rights Reserved[cite: 1].</p>
                <p class="text-amber-400 font-medium">Demonstration Prototype — Modernized Portal with Citizen AI Assistance</p>
            </div>
        </div>
    </footer>

    <!-- JAVASCRIPT APPLICATION CORE -->
    <script>
        const fdaData = {
            services: [
                {
                    id: 'food-licence',
                    name: 'Food Registration & Licensing (FoSCoS)',
                    category: 'Food',
                    desc: 'Mandatory registration or licensing for food businesses, manufacturers, restaurants, and petty vendors in Maharashtra[cite: 1].',
                    who: 'Food Business Operators, restaurants, manufacturers, and food vendors[cite: 1].',
                    url: 'http://foscos.fassai.gov.in/'
                },
                {
                    id: 'drug-licence',
                    name: 'Drug & Cosmetics Certificates (XLNIndia / FDA Mfg)',
                    category: 'Drug',
                    desc: 'Application portal for new drug manufacturing, wholesale/retail sales licences, and cosmetics certification[cite: 1].',
                    who: 'Pharmaceutical manufacturers, wholesale/retail chemists, and cosmetic producers[cite: 1].',
                    url: 'https://fdamfg.maharashtra.gov.in/'
                },
                {
                    id: 'who-gmp',
                    name: 'WHO-GMP Certificate Portal',
                    category: 'Drug',
                    desc: 'Application and verification portal for Good Manufacturing Practice certificates for international export compliance[cite: 1].',
                    who: 'Export-oriented pharmaceutical manufacturing units in Maharashtra[cite: 1].',
                    url: 'https://fdawhogmp.maharashtra.gov.in/'
                },
                {
                    id: 'community-food',
                    name: 'Community Food Distribution Permission',
                    category: 'Food',
                    desc: 'Special short-term permissions for large-scale community food distribution during festivals and public gatherings[cite: 1].',
                    who: 'Event organizers, religious trusts, and community committees[cite: 1].',
                    url: 'https://festivals.mahafda.in/'
                },
                {
                    id: 'grievance',
                    name: 'Online Grievance Registration',
                    category: 'General',
                    desc: 'Direct official channel to log formal complaints regarding food adulteration, substandard drugs, or cosmetics[cite: 1].',
                    who: 'Citizens, consumer forums, and whistleblowers[cite: 1].',
                    url: 'https://complaints.mahafda.in/'
                },
                {
                    id: 'aaple-sarkar',
                    name: 'Aaple Sarkar Portal Integration',
                    category: 'General',
                    desc: 'Single-window clearance for new manufacturing and sales users as directed by MEDD[cite: 1].',
                    who: 'New business registrants and license applicants[cite: 1].',
                    url: 'https://aaplesarkar.mahaonline.gov.in/en'
                }
            ],
            alerts: [
                {
                    id: 'coldrif-syrup',
                    title: 'Public Alert - Stop Use: Coldrif Syrup (Batch No. SR-13)',
                    product: 'Coldrif Syrup (Batch No. SR-13)',
                    batch: 'SR-13',
                    date: 'October 2025[cite: 1]',
                    desc: 'Issued due to toxic adulteration with Diethylene Glycol, following reports of child fatalities in Madhya Pradesh. Do not consume or distribute[cite: 1].',
                    source: 'Maharashtra FDA Official Press Note[cite: 1]',
                    url: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/10/202510082110815692.pdf'
                },
                {
                    id: 'blood-centre',
                    title: 'Blood Centre Compliance Order',
                    product: 'Blood Banks & Centres',
                    batch: 'N/A',
                    date: '2026[cite: 1]',
                    desc: 'Strict operational compliance guidelines and quality control standards issued for all licensed blood distribution centers across Maharashtra[cite: 1].',
                    source: 'Maharashtra FDA Circular[cite: 1]',
                    url: 'https://fda.maharashtra.gov.in/notice/blood-centre-compliance-order/'
                },
                {
                    id: 'school-food',
                    title: 'Safe Food for Every School Child in Maharashtra',
                    product: 'School Canteens & Mid-day Meals',
                    batch: 'N/A',
                    date: '2026[cite: 1]',
                    desc: 'Statewide order to strictly enforce 2020 Food Safety Regulations across all school canteens and mess facilities[cite: 1].',
                    source: 'Statewide Enforcement Order[cite: 1]',
                    url: 'https://fda.maharashtra.gov.in/notice/safe-food-for-every-school-child-in-maharashtra-statewide-order-to-enforce-the-2020-food-safety-regulations/'
                }
            ],
            notices: [
                { id: 'n1', title: 'Disclosure of Examination Marks – Class C (Senior Technical Assistant and Analytical Chemist Marksheet)', category: 'Recruitment', date: 'October 2025[cite: 1]', url: 'https://fda.maharashtra.gov.in/notice-category/announcements-general/' },
                { id: 'n2', title: 'Result Release for Group-B (Non-Gazetted) Posts including Analytical Chemist', category: 'Recruitment', date: 'October 2025[cite: 1]', url: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/10/202510101869944420.pdf' },
                { id: 'n3', title: 'Result Release for Group-C Posts including Senior Technical Assistant', category: 'Recruitment', date: 'October 2025[cite: 1]', url: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/10/20251010395535118.pdf' },
                { id: 'n4', title: 'Mandatory Login Creation and Application via Aaple Sarkar Portal for New Users', category: 'Circulars', date: '2026[cite: 1]', url: 'https://aaplesarkar.mahaonline.gov.in/en' },
                { id: 'n5', title: 'Successful Migration of XLNIndia Application to Fully Operational State', category: 'Orders', date: '2026[cite: 1]', url: 'https://fdamfg.maharashtra.gov.in/' }
            ],
            directory: {
                leadership: [
                    { name: 'Shri. Devendra Sarita Gangadharrao Fadnavis', desig: 'Hon’ble Chief Minister', role: 'Government Leadership', img: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/03/20250327318258923.jpeg' },
                    { name: 'Shri. Eknath Gangubai Sambhaji Shinde', desig: 'Hon’ble Deputy Chief Minister', role: 'Government Leadership', img: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/03/20250327978186677.jpeg' },
                    { name: 'Smt. Sunetra Ajit Pawar', desig: 'Hon’ble Deputy Chief Minister', role: 'Government Leadership', img: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2026/02/20260208937232249.jpeg' },
                    { name: 'Shri. Narhari Savitribai Sitaram Zirwal', desig: 'Hon\'ble Minister', role: 'Government Leadership', img: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/04/202504281673913987.jpeg' },
                    { name: 'Shri. Yogesh Kadam', desig: 'Hon\'ble State Minister', role: 'Government Leadership', img: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/04/202504281747070884.jpeg' }
                ],
                department: [
                    { name: 'Shri. Sanjay Khandare, IAS', desig: 'Additional Chief Secretary', role: 'Food and Drugs Department, Maharashtra[cite: 1]', img: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2026/05/20260527970484150.jpeg' },
                    { name: 'Shri. Tukaram Mundhe, IAS', desig: 'Commissioner', role: 'Food and Drug Administration, Maharashtra[cite: 1]', img: 'https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2026/05/202605271154254044.jpeg' }
                ]
            }
        };

        function searchFDAData(query) {
            const q = query.toLowerCase().trim();
            const results = { services: [], alerts: [], notices: [], directory: [] };
            if(!q) return results;

            results.services = fdaData.services.filter(s => s.name.toLowerCase().includes(q) || s.desc.toLowerCase().includes(q) || s.category.toLowerCase().includes(q) || s.who.toLowerCase().includes(q));
            results.alerts = fdaData.alerts.filter(a => a.title.toLowerCase().includes(q) || a.desc.toLowerCase().includes(q) || a.product.toLowerCase().includes(q));
            results.notices = fdaData.notices.filter(n => n.title.toLowerCase().includes(q) || n.category.toLowerCase().includes(q));
            results.directory = fdaData.directory.department.filter(d => d.name.toLowerCase().includes(q) || d.desig.toLowerCase().includes(q)).concat(
                fdaData.directory.leadership.filter(l => l.name.toLowerCase().includes(q) || l.desig.toLowerCase().includes(q))
            );
            return results;
        }

        async function askFDAAI(userMessage, context) {
            const retrieved = searchFDAData(userMessage);
            let answer = "I couldn't find this information in the available FDA data. Please verify through the official Maharashtra FDA portal[cite: 1].";
            let intent = "general_query";
            let category = "General";
            let issue = "General Inquiry";
            let priority = "Low";
            let confidence = 92;
            let recommended_action = "Consult official portal or lodge grievance.";
            let required_information = [];
            let source_ids = [];

            const q = userMessage.toLowerCase();

            if (q.includes('complaint') || q.includes('grievance') || q.includes('report') || q.includes('adulteration') || q.includes('expired')) {
                intent = "complaint_routing";
                category = q.includes('food') ? 'Food' : (q.includes('cosmetic') ? 'Cosmetic' : 'Drug');
                issue = "Reported violation / grievance in Maharashtra";
                priority = "High";
                confidence = 96;
                recommended_action = "Lodge official grievance online via complaints.mahafda.in[cite: 1].";
                required_information = ["Product Name", "Batch Number", "Purchase Location", "Bill / Proof"];
                source_ids = ["https://complaints.mahafda.in/"];
                answer = `You can log a formal ${category.toLowerCase()} complaint through the official Maharashtra FDA Online Grievance Portal[cite: 1]. Our system will route it for officer review.`;
            } else if (q.includes('licence') || q.includes('license') || q.includes('register') || q.includes('foscos') || q.includes('xlnindia')) {
                intent = "service_discovery";
                category = q.includes('food') ? 'Food' : 'Drug';
                priority = "Medium";
                confidence = 98;
                recommended_action = "Access official licensing portal[cite: 1].";
                source_ids = [q.includes('food') ? 'http://foscos.fassai.gov.in/' : 'https://fdamfg.maharashtra.gov.in/'];
                answer = q.includes('food') 
                    ? "Food business registrations and licences are processed via the FoSCoS FSSAI portal[cite: 1]."
                    : "Drug manufacturing and sales licences are managed through the XLNIndia / FDA Mfg portal[cite: 1].";
            } else if (q.includes('alert') || q.includes('coldrif') || q.includes('recall') || q.includes('nsq')) {
                intent = "safety_alert";
                category = "Drug";
                priority = "Critical";
                confidence = 99;
                recommended_action = "Review official safety alert notice and stop use immediately[cite: 1].";
                source_ids = ["https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/10/202510082110815692.pdf"];
                answer = "Maharashtra FDA issued a 'Public Alert - Stop Use' notice for Coldrif Syrup (Batch No. SR-13) due to toxic Diethylene Glycol adulteration[cite: 1].";
            } else if (q.includes('directory') || q.includes('officer') || q.includes('commissioner') || q.includes('mundhe') || q.includes('khandare')) {
                intent = "directory_lookup";
                confidence = 99;
                answer = "Shri. Tukaram Mundhe, IAS, serves as the Commissioner of Maharashtra FDA, and Shri. Sanjay Khandare, IAS, is the Additional Chief Secretary[cite: 1].";
                source_ids = ["https://fda.maharashtra.gov.in/food-safety-officers-directory/"];
            } else if (retrieved.services.length > 0) {
                intent = "service_match";
                category = retrieved.services[0].category;
                confidence = 95;
                answer = `Matched Service: ${retrieved.services[0].name}. ${retrieved.services[0].desc}`;
                source_ids = [retrieved.services[0].url];
            }

            return { intent, answer, category, issue, priority, confidence, recommended_action, required_information, source_ids };
        }

        async function analyzeComplaint(description) {
            const desc = description.toLowerCase();
            let cat = "Drug";
            let issue = "Substandard or expired pharmaceutical product";
            let priority = "High";
            let product = "Medicine / Pharmaceutical";
            let department = "Drug Regulation Department";
            let summary = description.slice(0, 120) + "...";
            let required_info = ["Medicine Name", "Batch Number", "Expiry Date", "Purchase Location", "Purchase Bill / Invoice"];

            if (desc.includes('food') || desc.includes('milk') || desc.includes('sweet') || desc.includes('restaurant') || desc.includes('hotel') || desc.includes('adulter')) {
                cat = "Food";
                issue = "Suspected food adulteration or unhygienic preparation";
                priority = "High";
                product = "Food Article / Dairy / Beverage";
                department = "Food Safety Directorate";
                required_info = ["Food Business Name", "Outlet Address", "Sample Photo", "Purchase Date"];
            } else if (desc.includes('cosmetic') || desc.includes('cream') || desc.includes('soap') || desc.includes('skin') || desc.includes('shampoo')) {
                cat = "Cosmetic";
                issue = "Adverse skin reaction or unlicensed cosmetic product";
                priority = "Medium";
                product = "Cosmetic Preparation";
                department = "Cosmetic Regulatory Wing";
                required_info = ["Cosmetic Brand Name", "Manufacturer Details", "Batch Number", "Medical Receipt"];
            } else if (desc.includes('expire') || desc.includes('spurious') || desc.includes('toxic') || desc.includes('child') || desc.includes('fatality')) {
                cat = "Drug";
                issue = "Critical drug adulteration or expired stock sale";
                priority = "Critical";
                product = "Prescription Medicine / Syrup";
                department = "State Intelligence & Enforcement Wing";
            }

            return { category: cat, issue: issue, product: product, location: "Mumbai / Maharashtra District", priority: priority, required_information: required_info, recommended_department: department, summary: summary, confidence: 96 };
        }

        async function explainFDAContent(noticeTitle, noticeDesc) {
            return {
                summary: `Official Maharashtra FDA Notice regarding: "${noticeTitle}". ${noticeDesc}`,
                target_audience: "All licensed Food Business Operators, Pharmaceutical Manufacturers, Chemists, and Citizens of Maharashtra.",
                key_points: [
                    "Mandatory compliance with Maharashtra FDA regulatory frameworks[cite: 1].",
                    "Strict prohibition of substandard, adulterated, or expired product distribution[cite: 1].",
                    "Requirement for timely online application/submission via designated state portals[cite: 1]."
                ]
            };
        }

        function findSimilarComplaints(currentComplaint) {
            return complaintsStore.filter(c => c.id !== currentComplaint.id && (c.category === currentComplaint.category || c.product.toLowerCase().includes(currentComplaint.product.toLowerCase().split(' ')[0]))).slice(0, 2);
        }

        let complaintsStore = [
            {
                id: 'MHFDA-2026-000001',
                category: 'Drug',
                issue: 'Possible expired medicine purchased from local chemist',
                product: 'Amoxicillin 500mg',
                location: 'Mumbai Central',
                date: '2026-09-24',
                priority: 'High — AI Recommendation',
                status: 'Under Review',
                assignedOfficer: 'Dr. R. K. Patil (Joint Commissioner - Drugs)',
                name: 'Aniket Deshmukh',
                mobile: '9876543210',
                email: 'aniket@example.com',
                description: 'Purchased antibiotics from chemist store. Expiry date was tampered with and medicine was expired.',
                aiAnalysis: {
                    category: 'Drug',
                    issue: 'Possible expired medicine / Tampered Expiry',
                    product: 'Amoxicillin 500mg',
                    priority: 'High — AI Recommendation',
                    required_information: ['Medicine name', 'Batch number', 'Expiry date', 'Purchase location', 'Purchase bill'],
                    recommended_department: 'Drug Regulation Department',
                    confidence: 96
                },
                officerDecision: {
                    action: 'Accepted & Inspection Dispatched',
                    modifiedCategory: 'Drug',
                    modifiedPriority: 'High — AI Recommendation',
                    overrideStatus: 'Accepted AI Recommendation'
                },
                history: ['Complaint Registered', 'AI Analysis Completed', 'Submitted for Officer Review', 'Officer Assigned']
            },
            {
                id: 'MHFDA-2026-000002',
                category: 'Food',
                issue: 'Suspected adulterated loose milk sold without branding',
                product: 'Loose Milk',
                location: 'Pune City',
                date: '2026-09-25',
                priority: 'High — AI Recommendation',
                status: 'Investigation / Inspection',
                assignedOfficer: 'S. V. Joshi (Food Safety Officer)',
                name: 'Priya Kulkarni',
                mobile: '9123456789',
                email: 'priya@example.com',
                description: 'Local dairy vendor selling unpasteurized loose milk with strange chemical smell and water adulteration.',
                aiAnalysis: {
                    category: 'Food',
                    issue: 'Suspected Milk Adulteration',
                    product: 'Loose Milk',
                    priority: 'High — AI Recommendation',
                    required_information: ['Vendor name', 'Shop address', 'Sample photo', 'Purchase date'],
                    recommended_department: 'Food Safety Directorate',
                    confidence: 98
                },
                officerDecision: {
                    action: 'Accepted & Inspection Dispatched',
                    modifiedCategory: 'Food',
                    modifiedPriority: 'High — AI Recommendation',
                    overrideStatus: 'Accepted AI Recommendation'
                },
                history: ['Complaint Registered', 'AI Analysis Completed', 'Submitted for Officer Review', 'Officer Assigned', 'Investigation / Inspection']
            },
            {
                id: 'MHFDA-2026-000003',
                category: 'Cosmetic',
                issue: 'Skin irritation and allergic reaction from unbranded face cream',
                product: 'Glow Fair Face Cream',
                location: 'Nagpur',
                date: '2026-09-26',
                priority: 'Medium',
                status: 'Complaint Registered',
                assignedOfficer: 'Unassigned',
                name: 'Rahul Verma',
                mobile: '9988776655',
                email: 'rahul@example.com',
                description: 'Purchased fairness cream from local shop. Caused severe chemical burn and skin rashes.',
                aiAnalysis: {
                    category: 'Cosmetic',
                    issue: 'Adverse Cosmetic Reaction / Unlicensed Product',
                    product: 'Glow Fair Face Cream',
                    priority: 'Medium',
                    required_information: ['Cosmetic name', 'Manufacturer details', 'Batch number', 'Medical prescription/bill'],
                    recommended_department: 'Cosmetic Regulatory Wing',
                    confidence: 91
                },
                officerDecision: {
                    action: 'Pending Review',
                    modifiedCategory: 'Cosmetic',
                    modifiedPriority: 'Medium',
                    overrideStatus: 'No Override (Pending)'
                },
                history: ['Complaint Registered', 'AI Analysis Completed']
            }
        ];

        const router = {
            routes: {
                '/': renderHome,
                '/services': renderServices,
                '/complaints': renderComplaints,
                '/alerts': renderAlerts,
                '/licences': renderLicences,
                '/notices': renderNotices,
                '/directory': renderDirectory,
                '/ai-assistant': renderAiAssistantPage,
                '/track-complaint': renderTrackComplaint,
                '/officer-dashboard': renderOfficerDashboard
            },
            navigateTo(path) {
                window.location.hash = path;
                this.handleRoute();
            },
            handleRoute() {
                let hash = window.location.hash.slice(1) || '/';
                const path = hash.split('?')[0];
                const renderFn = this.routes[path] || renderHome;
                
                document.querySelectorAll('.nav-link').forEach(el => {
                    if(el.getAttribute('data-route') === path) {
                        el.classList.add('bg-govblue-900', 'text-amber-300', 'font-bold');
                    } else {
                        el.classList.remove('bg-govblue-900', 'text-amber-300', 'font-bold');
                    }
                });

                renderFn();
                window.scrollTo(0, 0);
            }
        };

        window.addEventListener('hashchange', () => router.handleRoute());
        window.addEventListener('DOMContentLoaded', () => router.handleRoute());

        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        /* --- HOMEPAGE (Information-dense Government Portal Style) --- */
        function renderHome() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <!-- Critical Safety Alert Banner -->
                <div class="bg-amber-100 border-b border-amber-300 py-2.5 px-3">
                    <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-2 text-xs">
                        <div class="flex items-center gap-2">
                            <i class="fa-solid fa-triangle-exclamation text-amber-700 text-base"></i>
                            <span class="font-bold text-amber-900">CRITICAL PUBLIC ALERT: Stop Use Notice for Coldrif Syrup (Batch No. SR-13) due to toxic Diethylene Glycol adulteration[cite: 1].</span>
                        </div>
                        <a href="https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2025/10/202510082110815692.pdf" target="_blank" class="bg-govblue-800 hover:bg-govblue-900 text-white font-bold px-3 py-1 rounded text-[11px] whitespace-nowrap">
                            View Official Press Note[cite: 1] <i class="fa-solid fa-external-link-alt ml-1"></i>
                        </a>
                    </div>
                </div>

                <div class="max-w-7xl mx-auto px-3 py-6 grid grid-cols-1 lg:grid-cols-4 gap-6">
                    <!-- Left Sidebar: Quick Navigation & Leadership -->
                    <div class="space-y-6">
                        <div class="bg-white rounded border border-slate-300 shadow-xs overflow-hidden">
                            <div class="bg-govblue-800 text-white px-3 py-2 text-xs font-bold uppercase tracking-wider">
                                Department Leadership
                            </div>
                            <div class="p-3 space-y-4 text-xs">
                                <div class="flex items-center gap-3 pb-3 border-b border-slate-200">
                                    <img src="https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2026/05/202605271154254044.jpeg" alt="Tukaram Mundhe" class="w-12 h-12 rounded object-cover border border-slate-300">
                                    <div>
                                        <p class="font-bold text-slate-900">Shri. Tukaram Mundhe, IAS[cite: 1]</p>
                                        <p class="text-slate-600 text-[11px]">Commissioner, FDA Maharashtra[cite: 1]</p>
                                    </div>
                                </div>
                                <div class="flex items-center gap-3">
                                    <img src="https://cdnbbsr.s3waas.gov.in/s3e14d02262d6510598edccb6180462efd/uploads/2026/05/20260527970484150.jpeg" alt="Sanjay Khandare" class="w-12 h-12 rounded object-cover border border-slate-300">
                                    <div>
                                        <p class="font-bold text-slate-900">Shri. Sanjay Khandare, IAS[cite: 1]</p>
                                        <p class="text-slate-600 text-[11px]">Additional Chief Secretary, MEDD[cite: 1]</p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="bg-white rounded border border-slate-300 shadow-xs overflow-hidden">
                            <div class="bg-govblue-800 text-white px-3 py-2 text-xs font-bold uppercase tracking-wider">
                                Citizen Services Quick Menu
                            </div>
                            <div class="p-2 space-y-1 text-xs">
                                <a href="#/services" onclick="router.navigateTo('/services')" class="block p-2 rounded hover:bg-slate-100 text-slate-700 font-medium flex items-center justify-between"><span class="flex items-center gap-2"><i class="fa-solid fa-utensils text-blue-700"></i> Food Licencing (FoSCoS)[cite: 1]</span><i class="fa-solid fa-chevron-right text-[10px] text-slate-400"></i></a>
                                <a href="#/services" onclick="router.navigateTo('/services')" class="block p-2 rounded hover:bg-slate-100 text-slate-700 font-medium flex items-center justify-between"><span class="flex items-center gap-2"><i class="fa-solid fa-pills text-blue-700"></i> Drug & Cosmetics Portals[cite: 1]</span><i class="fa-solid fa-chevron-right text-[10px] text-slate-400"></i></a>
                                <a href="#/complaints" onclick="router.navigateTo('/complaints')" class="block p-2 rounded hover:bg-slate-100 text-slate-700 font-medium flex items-center justify-between"><span class="flex items-center gap-2"><i class="fa-solid fa-file-pen text-blue-700"></i> Lodge Online Grievance[cite: 1]</span><i class="fa-solid fa-chevron-right text-[10px] text-slate-400"></i></a>
                                <a href="#/track-complaint" onclick="router.navigateTo('/track-complaint')" class="block p-2 rounded hover:bg-slate-100 text-slate-700 font-medium flex items-center justify-between"><span class="flex items-center gap-2"><i class="fa-solid fa-magnifying-glass text-blue-700"></i> Track Complaint Status</span><i class="fa-solid fa-chevron-right text-[10px] text-slate-400"></i></a>
                            </div>
                        </div>
                    </div>

                    <!-- Center & Right: Main Portal Content & Smart Service Finder -->
                    <div class="lg:col-span-3 space-y-6">
                        <!-- Hero Search Box (Govt Service Finder) -->
                        <div class="bg-white rounded border border-slate-300 shadow-xs p-5">
                            <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider mb-2 flex items-center gap-2">
                                <img src="https://upload.wikimedia.org/wikipedia/commons/2/26/Seal_of_Maharashtra.svg" alt="Emblem" class="w-5 h-5 object-contain"> Maharashtra FDA Citizen Service Portal
                            </h2>
                            <p class="text-xs text-slate-600 mb-4">Search official services, licences, or report grievances naturally using our AI service assistant[cite: 1].</p>
                            
                            <div class="flex flex-col sm:flex-row gap-2">
                                <div class="relative flex-grow">
                                    <i class="fa-solid fa-search absolute left-3 top-3 text-slate-400 text-xs"></i>
                                    <input type="text" id="home-search-input" placeholder="e.g. 'I want a food licence', 'expired medicine complaint'..." class="w-full pl-9 pr-3 py-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700" onkeydown="if(event.key==='Enter') executeHomeSearch()">
                                </div>
                                <button onclick="executeHomeSearch()" class="bg-govblue-800 hover:bg-govblue-900 text-white px-5 py-2 rounded text-xs font-bold transition-colors">
                                    Search Services
                                </button>
                            </div>
                            <div id="home-search-result-area" class="mt-3 text-xs hidden"></div>
                        </div>

                        <!-- Important Notices & Announcements Table -->
                        <div class="bg-white rounded border border-slate-300 shadow-xs overflow-hidden">
                            <div class="bg-govblue-800 text-white px-4 py-2.5 text-xs font-bold uppercase tracking-wider flex justify-between items-center">
                                <span>Latest Updates & Notices[cite: 1]</span>
                                <a href="#/notices" onclick="router.navigateTo('/notices')" class="text-amber-300 hover:underline text-[11px]">View All Notices</a>
                            </div>
                            <div class="divide-y divide-slate-200 text-xs">
                                ${fdaData.notices.slice(0, 4).map(notice => `
                                    <div class="p-3 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2 hover:bg-slate-50">
                                        <div>
                                            <span class="inline-block bg-blue-100 text-blue-800 text-[10px] font-bold px-2 py-0.5 rounded mr-2">${notice.category}</span>
                                            <span class="text-slate-800 font-medium">${notice.title}</span>
                                        </div>
                                        <a href="${notice.url}" target="_blank" class="text-blue-700 hover:underline text-[11px] whitespace-nowrap font-semibold">
                                            Official Link[cite: 1] <i class="fa-solid fa-external-link-alt text-[9px]"></i>
                                        </a>
                                    </div>
                                `).join('')}
                            </div>
                        </div>

                        <!-- Official Portals Grid -->
                        <div class="bg-white rounded border border-slate-300 shadow-xs p-5">
                            <h3 class="text-xs font-bold uppercase tracking-wider text-govblue-900 mb-3 border-b border-slate-200 pb-2">Verified Government Portals[cite: 1]</h3>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
                                ${fdaData.services.slice(0, 4).map(s => `
                                    <div class="p-3 rounded border border-slate-200 bg-slate-50 flex flex-col justify-between">
                                        <div>
                                            <span class="text-[10px] font-bold text-blue-800 bg-blue-100 px-2 py-0.5 rounded">${s.category}</span>
                                            <h4 class="font-bold text-slate-900 mt-1.5 mb-1">${s.name}</h4>
                                            <p class="text-[11px] text-slate-600 line-clamp-2">${s.desc}</p>
                                        </div>
                                        <div class="mt-3 pt-2 border-t border-slate-200 flex justify-between items-center">
                                            <span class="text-[10px] text-slate-500 truncate max-w-[120px] font-mono">${s.url}</span>
                                            <a href="${s.url}" target="_blank" class="bg-govblue-800 hover:bg-govblue-900 text-white text-[11px] font-bold px-3 py-1 rounded">
                                                Open Portal[cite: 1] <i class="fa-solid fa-external-link-alt text-[9px]"></i>
                                            </a>
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                        </div>
                    </div>
                </div>
            `;
        }

        async function executeHomeSearch() {
            const query = document.getElementById('home-search-input').value.trim();
            const resultArea = document.getElementById('home-search-result-area');
            if(!query) {
                resultArea.classList.add('hidden');
                return;
            }

            const aiResponse = await askFDAAI(query);
            const retrieved = searchFDAData(query);
            
            resultArea.classList.remove('hidden');
            if(retrieved.services.length > 0) {
                const match = retrieved.services[0];
                resultArea.innerHTML = `
                    <div class="bg-blue-50 border border-blue-200 p-3 rounded">
                        <div class="flex items-center justify-between mb-1">
                            <span class="font-bold text-blue-900">${match.name}</span>
                            <span class="text-[10px] bg-blue-200 text-blue-900 px-1.5 py-0.5 rounded">Matched Service</span>
                        </div>
                        <p class="text-slate-700 text-[11px] mb-2">${match.desc}</p>
                        <a href="${match.url}" target="_blank" class="inline-flex items-center gap-1 bg-govblue-800 text-white px-3 py-1 rounded font-bold text-[11px]">
                            Open Official Portal[cite: 1] <i class="fa-solid fa-external-link-alt text-[9px]"></i>
                        </a>
                    </div>
                `;
            } else {
                resultArea.innerHTML = `
                    <div class="bg-slate-50 border border-slate-200 p-3 rounded text-slate-700">
                        <p class="font-bold mb-1"><i class="fa-solid fa-robot text-blue-700 mr-1"></i> AI Service Assistant Guidance:</p>
                        <p class="text-[11px] mb-2">${aiResponse.answer}</p>
                        <button onclick="router.navigateTo('/complaints')" class="bg-govblue-800 text-white px-3 py-1 rounded text-[11px] font-bold">Lodge Grievance Online[cite: 1]</button>
                    </div>
                `;
            }
        }

        /* --- SERVICES PAGE --- */
        function renderServices() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <div class="max-w-7xl mx-auto px-3 py-6 space-y-4">
                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider">Official Services & Portals Directory[cite: 1]</h2>
                        <p class="text-xs text-slate-600 mt-1">Access verified official government portals for food business registration, drug manufacturing licences, and regulatory certificates[cite: 1].</p>
                        
                        <div class="mt-3">
                            <input type="text" id="services-ai-input" placeholder="Search official services..." class="w-full sm:w-80 px-3 py-1.5 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700" oninput="filterServicesDynamic()">
                        </div>
                    </div>

                    <div id="services-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4"></div>
                </div>
            `;
            renderServicesList(fdaData.services);
        }

        function renderServicesList(servicesArray) {
            const grid = document.getElementById('services-grid');
            if(!grid) return;
            if(servicesArray.length === 0) {
                grid.innerHTML = `<div class="col-span-3 text-center py-8 text-slate-500 text-xs">No matching official services found in the database.</div>`;
                return;
            }
            grid.innerHTML = servicesArray.map(s => `
                <div class="bg-white rounded border border-slate-300 p-4 shadow-xs flex flex-col justify-between text-xs">
                    <div>
                        <div class="flex items-center justify-between mb-2">
                            <span class="bg-blue-100 text-blue-800 font-bold px-2 py-0.5 rounded text-[10px]">${s.category}</span>
                            <span class="text-[10px] text-emerald-700 font-semibold"><i class="fa-solid fa-check-circle"></i> Verified Portal[cite: 1]</span>
                        </div>
                        <h3 class="font-bold text-slate-900 text-sm mb-1.5">${s.name}</h3>
                        <p class="text-slate-600 text-[11px] mb-3 leading-relaxed">${s.desc}</p>
                        <div class="bg-slate-50 p-2.5 rounded border border-slate-200 text-[11px] text-slate-700 mb-3">
                            <strong class="text-slate-900 block mb-0.5">Who may need it:[cite: 1]</strong>
                            ${s.who}
                        </div>
                    </div>
                    <div class="pt-2 border-t border-slate-200 flex items-center justify-between">
                        <span class="text-[10px] text-slate-400 font-mono truncate max-w-[140px]">${s.url}</span>
                        <a href="${s.url}" target="_blank" class="bg-govblue-800 hover:bg-govblue-900 text-white font-bold px-3 py-1.5 rounded text-[11px] shadow-xs flex items-center gap-1">
                            <span>Open Portal[cite: 1]</span>
                            <i class="fa-solid fa-external-link-alt text-[9px]"></i>
                        </a>
                    </div>
                </div>
            `).join('');
        }

        function filterServicesDynamic() {
            const query = document.getElementById('services-ai-input').value;
            const retrieved = searchFDAData(query);
            renderServicesList(retrieved.services.length > 0 ? retrieved.services : fdaData.services);
        }

        /* --- COMPLAINTS PAGE --- */
        let complaintFormState = {
            step: 1,
            description: '',
            aiAnalysis: null,
            formData: { name: '', mobile: '', email: '', category: 'Drug', product: '', location: '', date: new Date().toISOString().split('T')[0] },
            submittedId: null
        };

        function renderComplaints() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <div class="max-w-4xl mx-auto px-3 py-6 space-y-4">
                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider">Online Grievance Redressal System</h2>
                        <p class="text-xs text-slate-600 mt-1">Submit complaints regarding food adulteration, substandard drugs, or cosmetics. AI assists in classification and routing for authorized officer review[cite: 1].</p>
                    </div>

                    <div id="complaint-wizard-container"></div>
                </div>
            `;
            renderComplaintStep();
        }

        async function renderComplaintStep() {
            const wiz = document.getElementById('complaint-wizard-container');
            if(!wiz) return;

            if(complaintFormState.step === 1) {
                wiz.innerHTML = `
                    <div class="bg-white rounded border border-slate-300 p-5 shadow-xs text-xs">
                        <div class="mb-4 pb-2 border-b border-slate-200">
                            <span class="text-[11px] font-bold text-blue-700 uppercase">Step 1 of 5: Complaint Description</span>
                            <h3 class="text-sm font-bold text-slate-900 mt-0.5">What happened?</h3>
                        </div>

                        <div class="space-y-3">
                            <textarea id="complaint-desc-input" rows="4" placeholder="Describe your issue in detail... e.g. 'I purchased medicine from local chemist and noticed it was expired.'" class="w-full p-3 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">${complaintFormState.description}</textarea>
                            
                            <div class="flex justify-between items-center pt-2">
                                <button type="button" onclick="startComplaintVoiceInput()" class="bg-slate-200 hover:bg-slate-300 text-slate-700 px-3 py-1.5 rounded font-semibold flex items-center gap-1.5">
                                    <i class="fa-solid fa-microphone text-blue-700"></i>
                                    <span id="complaint-voice-btn-text">Voice Input</span>
                                </button>
                                <button type="button" onclick="processComplaintStep1()" class="bg-govblue-800 hover:bg-govblue-900 text-white px-5 py-2 rounded font-bold shadow-xs">
                                    Analyze with AI <i class="fa-solid fa-arrow-right ml-1"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                `;
            } else if(complaintFormState.step === 2) {
                const analysis = complaintFormState.aiAnalysis;
                wiz.innerHTML = `
                    <div class="bg-white rounded border border-slate-300 p-5 shadow-xs text-xs">
                        <div class="mb-4 pb-2 border-b border-slate-200 flex justify-between items-center">
                            <div>
                                <span class="text-[11px] font-bold text-blue-700 uppercase">Step 2 of 5: AI Analysis</span>
                                <h3 class="text-sm font-bold text-slate-900 mt-0.5">Classification & Routing Recommendation</h3>
                            </div>
                            <span class="bg-emerald-100 text-emerald-800 font-bold px-2 py-0.5 rounded text-[10px]">Confidence: ${analysis.confidence}%</span>
                        </div>

                        <div class="bg-slate-50 rounded border border-slate-200 p-4 space-y-3 mb-4">
                            <div class="grid grid-cols-2 gap-3">
                                <div><span class="text-slate-500 block">Category</span><strong class="text-slate-900">${analysis.category}</strong></div>
                                <div><span class="text-slate-500 block">Priority Recommendation</span><strong class="text-orange-700">${analysis.priority}</strong></div>
                                <div><span class="text-slate-500 block">Identified Issue</span><strong class="text-slate-800">${analysis.issue}</strong></div>
                                <div><span class="text-slate-500 block">Recommended Department</span><strong class="text-blue-900">${analysis.recommended_department}</strong></div>
                            </div>
                            <div class="pt-2 border-t border-slate-200">
                                <span class="text-slate-500 block mb-1">Required Information Extracted[cite: 1]:</span>
                                <div class="flex flex-wrap gap-1">
                                    ${analysis.required_information.map(info => `<span class="bg-white px-2 py-0.5 rounded text-[11px] font-medium text-slate-700 border border-slate-300">${info}</span>`).join('')}
                                </div>
                            </div>
                        </div>

                        <div class="bg-amber-50 border border-amber-300 p-3 rounded mb-4 text-amber-900 text-[11px]">
                            <strong>Notice:[cite: 1]</strong> AI-generated recommendation. Final classification, routing and enforcement decisions require authorized officer review[cite: 1].
                        </div>

                        <div class="flex justify-between items-center">
                            <button type="button" onclick="complaintFormState.step=1; renderComplaintStep();" class="text-slate-700 font-semibold">
                                <i class="fa-solid fa-arrow-left mr-1"></i> Edit Description
                            </button>
                            <button type="button" onclick="processComplaintStep2()" class="bg-govblue-800 hover:bg-govblue-900 text-white px-5 py-2 rounded font-bold shadow-xs">
                                Continue to Form <i class="fa-solid fa-arrow-right ml-1"></i>
                            </button>
                        </div>
                    </div>
                `;
            } else if(complaintFormState.step === 3) {
                const fd = complaintFormState.formData;
                wiz.innerHTML = `
                    <div class="bg-white rounded border border-slate-300 p-5 shadow-xs text-xs">
                        <div class="mb-4 pb-2 border-b border-slate-200">
                            <span class="text-[11px] font-bold text-blue-700 uppercase">Step 3 of 5: Structured Details</span>
                            <h3 class="text-sm font-bold text-slate-900 mt-0.5">Complainant & Incident Information</h3>
                        </div>

                        <form onsubmit="processComplaintStep3(event)" class="space-y-3">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Full Name *</label>
                                    <input type="text" id="c-name" required value="${fd.name}" class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">
                                </div>
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Mobile Number *</label>
                                    <input type="tel" id="c-mobile" required value="${fd.mobile}" class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">
                                </div>
                            </div>

                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Email Address</label>
                                    <input type="email" id="c-email" value="${fd.email}" class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">
                                </div>
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Category *</label>
                                    <select id="c-category" class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700 bg-white">
                                        <option value="Drug" ${fd.category==='Drug'?'selected':''}>Drug / Pharmaceutical</option>
                                        <option value="Food" ${fd.category==='Food'?'selected':''}>Food & Adulteration</option>
                                        <option value="Cosmetic" ${fd.category==='Cosmetic'?'selected':''}>Cosmetic</option>
                                    </select>
                                </div>
                            </div>

                            <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Product / Item *</label>
                                    <input type="text" id="c-product" required value="${fd.product}" class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">
                                </div>
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Location / Area *</label>
                                    <input type="text" id="c-location" required value="${fd.location}" class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">
                                </div>
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Incident Date *</label>
                                    <input type="date" id="c-date" required value="${fd.date}" class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">
                                </div>
                            </div>

                            <div>
                                <label class="block font-bold text-slate-700 mb-1">Complaint Description *</label>
                                <textarea id="c-desc" rows="3" required class="w-full p-2 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700">${complaintFormState.description}</textarea>
                            </div>

                            <div>
                                <label class="block font-bold text-slate-700 mb-1">Upload Supporting Evidence (Photo / Bill)</label>
                                <input type="file" class="w-full p-1.5 rounded border border-slate-300 text-[11px] bg-slate-50">
                            </div>

                            <div class="flex justify-between items-center pt-2">
                                <button type="button" onclick="complaintFormState.step=2; renderComplaintStep();" class="text-slate-700 font-semibold">
                                    <i class="fa-solid fa-arrow-left mr-1"></i> Back
                                </button>
                                <button type="submit" class="bg-govblue-800 hover:bg-govblue-900 text-white px-5 py-2 rounded font-bold shadow-xs">
                                    Review Complaint <i class="fa-solid fa-arrow-right ml-1"></i>
                                </button>
                            </div>
                        </form>
                    </div>
                `;
            } else if(complaintFormState.step === 4) {
                const fd = complaintFormState.formData;
                wiz.innerHTML = `
                    <div class="bg-white rounded border border-slate-300 p-5 shadow-xs text-xs">
                        <div class="mb-4 pb-2 border-b border-slate-200">
                            <span class="text-[11px] font-bold text-blue-700 uppercase">Step 4 of 5: Final Review</span>
                            <h3 class="text-sm font-bold text-slate-900 mt-0.5">Verify Information</h3>
                        </div>

                        <div class="bg-slate-50 rounded border border-slate-200 p-4 space-y-2.5 mb-4">
                            <div class="grid grid-cols-2 gap-3 pb-2 border-b border-slate-200">
                                <div><span class="text-slate-500 block">Complainant Name</span><strong class="text-slate-900">${fd.name}</strong></div>
                                <div><span class="text-slate-500 block">Mobile Number</span><strong class="text-slate-900">${fd.mobile}</strong></div>
                            </div>
                            <div class="grid grid-cols-2 gap-3 pb-2 border-b border-slate-200">
                                <div><span class="text-slate-500 block">Category & Product</span><strong class="text-slate-900">${fd.category} — ${fd.product}</strong></div>
                                <div><span class="text-slate-500 block">Location & Date</span><strong class="text-slate-900">${fd.location} (${fd.date})</strong></div>
                            </div>
                            <div>
                                <span class="text-slate-500 block">Description</span>
                                <p class="text-slate-800 mt-0.5">${complaintFormState.description}</p>
                            </div>
                        </div>

                        <div class="flex justify-between items-center">
                            <button type="button" onclick="complaintFormState.step=3; renderComplaintStep();" class="text-slate-700 font-semibold">
                                <i class="fa-solid fa-arrow-left mr-1"></i> Edit Details
                            </button>
                            <button type="button" onclick="submitFinalComplaint()" class="bg-emerald-700 hover:bg-emerald-800 text-white px-5 py-2 rounded font-bold shadow-xs">
                                <i class="fa-solid fa-check mr-1"></i> Submit Official Grievance
                            </button>
                        </div>
                    </div>
                `;
            } else if(complaintFormState.step === 5) {
                wiz.innerHTML = `
                    <div class="bg-white rounded border border-slate-300 p-6 text-center text-xs shadow-xs">
                        <div class="w-12 h-12 bg-emerald-100 text-emerald-700 rounded-full flex items-center justify-center text-xl mx-auto mb-3">
                            <i class="fa-solid fa-circle-check"></i>
                        </div>
                        <h3 class="text-sm font-bold text-slate-900 mb-1">Grievance Registered Successfully</h3>
                        <p class="text-slate-600 mb-4">Your complaint has been securely logged into the Maharashtra FDA database.</p>

                        <div class="bg-slate-50 p-4 rounded border border-slate-200 max-w-sm mx-auto mb-4 text-left space-y-2">
                            <div class="flex justify-between items-center pb-2 border-b border-slate-200">
                                <span class="text-slate-500">Complaint ID[cite: 1]:</span>
                                <span class="font-mono font-bold text-blue-700 bg-blue-50 px-2 py-0.5 rounded border border-blue-200">${complaintFormState.submittedId}</span>
                            </div>
                            <div class="flex justify-between items-center pb-2 border-b border-slate-200">
                                <span class="text-slate-500">Category:</span>
                                <strong class="text-slate-800">${complaintFormState.formData.category}</strong>
                            </div>
                            <div class="flex justify-between items-center">
                                <span class="text-slate-500">Status:[cite: 1]</span>
                                <span class="bg-amber-100 text-amber-800 font-bold px-2 py-0.5 rounded text-[10px]">Submitted for Officer Review[cite: 1]</span>
                            </div>
                        </div>

                        <div class="flex justify-center gap-2">
                            <button onclick="router.navigateTo('/track-complaint')" class="bg-govblue-800 text-white px-4 py-2 rounded font-bold">Track Status</button>
                            <button onclick="resetComplaintWizard()" class="bg-slate-200 text-slate-700 px-4 py-2 rounded font-bold">Lodge Another</button>
                        </div>
                    </div>
                `;
            }
        }

        function startComplaintVoiceInput() {
            if (!('webkitSpeechRecognition' in window) && !('SpeechRecognition' in window)) {
                alert("Voice input is not supported in this browser.");
                return;
            }
            const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
            const recognition = new SpeechRecognition();
            recognition.lang = 'en-IN';
            const btnText = document.getElementById('complaint-voice-btn-text');
            btnText.innerText = "Listening...";
            recognition.onresult = (event) => {
                document.getElementById('complaint-desc-input').value = event.results[0][0].transcript;
                btnText.innerText = "Voice Input";
            };
            recognition.onerror = () => { btnText.innerText = "Error"; };
            recognition.start();
        }

        async function processComplaintStep1() {
            const desc = document.getElementById('complaint-desc-input').value.trim();
            if(!desc) { alert("Please describe your problem."); return; }
            complaintFormState.description = desc;
            complaintFormState.aiAnalysis = await analyzeComplaint(desc);
            complaintFormState.formData.category = complaintFormState.aiAnalysis.category;
            complaintFormState.formData.product = complaintFormState.aiAnalysis.product;
            complaintFormState.step = 2;
            renderComplaintStep();
        }

        function processComplaintStep2() { complaintFormState.step = 3; renderComplaintStep(); }

        function processComplaintStep3(e) {
            e.preventDefault();
            complaintFormState.formData.name = document.getElementById('c-name').value;
            complaintFormState.formData.mobile = document.getElementById('c-mobile').value;
            complaintFormState.formData.email = document.getElementById('c-email').value;
            complaintFormState.formData.category = document.getElementById('c-category').value;
            complaintFormState.formData.product = document.getElementById('c-product').value;
            complaintFormState.formData.location = document.getElementById('c-location').value;
            complaintFormState.formData.date = document.getElementById('c-date').value;
            complaintFormState.description = document.getElementById('c-desc').value;
            complaintFormState.step = 4;
            renderComplaintStep();
        }

        function submitFinalComplaint() {
            const newId = 'MHFDA-2026-0000' + (complaintsStore.length + 1);
            complaintFormState.submittedId = newId;
            complaintsStore.unshift({
                id: newId,
                category: complaintFormState.formData.category,
                issue: complaintFormState.aiAnalysis.issue,
                product: complaintFormState.formData.product,
                location: complaintFormState.formData.location,
                date: complaintFormState.formData.date,
                priority: complaintFormState.aiAnalysis.priority,
                status: 'Submitted for Officer Review',
                assignedOfficer: 'Unassigned',
                name: complaintFormState.formData.name,
                mobile: complaintFormState.formData.mobile,
                email: complaintFormState.formData.email,
                description: complaintFormState.description,
                aiAnalysis: complaintFormState.aiAnalysis,
                officerDecision: { action: 'Pending Review', modifiedCategory: complaintFormState.formData.category, modifiedPriority: complaintFormState.aiAnalysis.priority, overrideStatus: 'No Override (Pending)' },
                history: ['Complaint Registered', 'AI Analysis Completed', 'Submitted for Officer Review']
            });
            complaintFormState.step = 5;
            renderComplaintStep();
        }

        function resetComplaintWizard() {
            complaintFormState = { step: 1, description: '', aiAnalysis: null, formData: { name: '', mobile: '', email: '', category: 'Drug', product: '', location: '', date: new Date().toISOString().split('T')[0] }, submittedId: null };
            renderComplaintStep();
        }

        /* --- SAFETY ALERTS PAGE --- */
        function renderAlerts() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <div class="max-w-7xl mx-auto px-3 py-6 space-y-4 text-xs">
                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider">Safety Alerts & Public Notices[cite: 1]</h2>
                        <p class="text-slate-600 mt-1">Official Stop-Use alerts, Not of Standard Quality (NSQ) drug notices, and safety advisories issued by Maharashtra FDA[cite: 1].</p>
                    </div>

                    <div class="space-y-3">
                        ${fdaData.alerts.map(alert => `
                            <div class="bg-white rounded border border-slate-300 p-4 shadow-xs flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
                                <div class="space-y-1.5 max-w-3xl">
                                    <div class="flex items-center gap-2">
                                        <span class="bg-amber-100 text-amber-900 font-bold px-2 py-0.5 rounded text-[10px]">CRITICAL ALERT</span>
                                        <span class="text-slate-500">${alert.date}</span>
                                        <span class="bg-slate-100 text-slate-700 px-2 py-0.5 rounded text-[10px]">Batch: ${alert.batch}</span>
                                    </div>
                                    <h3 class="font-bold text-slate-900 text-sm">${alert.title}</h3>
                                    <p class="text-slate-600 text-[11px] leading-relaxed">${alert.desc}</p>
                                    <p class="text-slate-500 text-[10px]"><strong>Source:</strong> ${alert.source}</p>
                                </div>
                                <div class="flex items-center gap-2 flex-shrink-0 w-full md:w-auto">
                                    <button onclick="openExplainNoticeModal('${alert.title}', '${alert.desc}')" class="bg-slate-200 hover:bg-slate-300 text-slate-800 font-bold px-3 py-1.5 rounded flex items-center gap-1">
                                        <i class="fa-solid fa-robot text-blue-700"></i> AI Explain
                                    </button>
                                    <a href="${alert.url}" target="_blank" class="bg-govblue-800 hover:bg-govblue-900 text-white font-bold px-4 py-1.5 rounded flex items-center gap-1">
                                        <span>View Notice</span>
                                        <i class="fa-solid fa-external-link-alt text-[9px]"></i>
                                    </a>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                </div>
            `;
        }

        async function openExplainNoticeModal(title, desc) {
            const explanation = await explainFDAContent(title, desc);
            const modalHTML = `
                <div id="explain-notice-modal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-xs z-50 flex items-center justify-center p-3">
                    <div class="bg-white rounded shadow-xl w-full max-w-lg overflow-hidden border border-slate-300 text-xs">
                        <div class="bg-govblue-900 text-white p-3 flex justify-between items-center">
                            <h3 class="font-bold flex items-center gap-2"><i class="fa-solid fa-robot text-amber-400"></i> Notice Summary (AI Assistant)</h3>
                            <button onclick="document.getElementById('explain-notice-modal').remove()" class="text-slate-300 hover:text-white"><i class="fa-solid fa-xmark"></i></button>
                        </div>
                        <div class="p-4 space-y-3 text-slate-700">
                            <div>
                                <strong class="text-slate-900 block mb-1">Summary:</strong>
                                <p class="bg-slate-50 p-2.5 rounded border border-slate-200">${explanation.summary}</p>
                            </div>
                            <div>
                                <strong class="text-slate-900 block mb-1">Target Audience:</strong>
                                <p class="bg-slate-50 p-2.5 rounded border border-slate-200">${explanation.target_audience}</p>
                            </div>
                            <div>
                                <strong class="text-slate-900 block mb-1">Key Points:[cite: 1]</strong>
                                <ul class="list-disc pl-4 space-y-1 bg-slate-50 p-2.5 rounded border border-slate-200">
                                    ${explanation.key_points.map(pt => `<li>${pt}</li>`).join('')}
                                </ul>
                            </div>
                            <div class="bg-amber-50 p-2.5 rounded border border-amber-200 text-amber-900 text-[10px]">
                                AI-generated summary. Read the original notice for authoritative information.
                            </div>
                            <div class="flex justify-end pt-2">
                                <button onclick="document.getElementById('explain-notice-modal').remove()" class="bg-govblue-800 text-white px-4 py-1.5 rounded font-bold">Close</button>
                            </div>
                        </div>
                    </div>
                </div>
            `;
            document.body.insertAdjacentHTML('beforeend', modalHTML);
        }

        /* --- LICENCES PAGE --- */
        function renderLicences() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <div class="max-w-7xl mx-auto px-3 py-6 space-y-4 text-xs">
                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider">Licences & Manufacturing Portals[cite: 1]</h2>
                        <p class="text-slate-600 mt-1">Official digital portals for food business registration, drug manufacturing licences, and WHO-GMP certifications[cite: 1].</p>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                        ${fdaData.services.map(s => `
                            <div class="bg-white rounded border border-slate-300 p-4 shadow-xs flex flex-col justify-between">
                                <div>
                                    <span class="bg-blue-100 text-blue-800 font-bold px-2 py-0.5 rounded text-[10px]">${s.category} Portal</span>
                                    <h3 class="font-bold text-slate-900 text-sm mt-2 mb-1">${s.name}</h3>
                                    <p class="text-slate-600 text-[11px] mb-3 leading-relaxed">${s.desc}</p>
                                </div>
                                <div class="pt-2 border-t border-slate-200">
                                    <a href="${s.url}" target="_blank" class="w-full bg-govblue-800 hover:bg-govblue-900 text-white font-bold py-2 rounded text-center block shadow-xs">
                                        Access Official Portal[cite: 1] <i class="fa-solid fa-external-link-alt text-[9px] ml-1"></i>
                                    </a>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                </div>
            `;
        }

        /* --- NOTICES PAGE --- */
        function renderNotices() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <div class="max-w-7xl mx-auto px-3 py-6 space-y-4 text-xs">
                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider">Notices, Circulars & Announcements[cite: 1]</h2>
                        <p class="text-slate-600 mt-1">Browse official Maharashtra FDA circulars, recruitment results, and administrative orders[cite: 1].</p>
                    </div>

                    <div class="bg-white rounded border border-slate-300 shadow-xs overflow-hidden">
                        <div class="p-3 bg-slate-50 border-b border-slate-200">
                            <input type="text" id="notice-filter-input" placeholder="Filter notices by keyword..." class="w-full sm:w-80 px-3 py-1.5 rounded border border-slate-300 text-xs focus:outline-none focus:border-blue-700" oninput="filterNoticesTable()">
                        </div>
                        <div class="divide-y divide-slate-200" id="notices-list-container">
                            ${fdaData.notices.map(n => `
                                <div class="p-4 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-3">
                                    <div class="space-y-1 max-w-3xl">
                                        <div class="flex items-center gap-2">
                                            <span class="bg-blue-100 text-blue-800 font-bold px-2 py-0.5 rounded text-[10px]">${n.category}</span>
                                            <span class="text-slate-500">${n.date}</span>
                                        </div>
                                        <h3 class="font-bold text-slate-900">${n.title}</h3>
                                    </div>
                                    <div class="flex items-center gap-2 flex-shrink-0">
                                        <button onclick="openExplainNoticeModal('${n.title}', 'Official notice published under${n.category}')" class="bg-slate-200 hover:bg-slate-300 text-slate-800 font-bold px-3 py-1.5 rounded">AI Explain</button>
                                        <a href="${n.url}" target="_blank" class="bg-govblue-800 text-white font-bold px-3 py-1.5 rounded">Original Link</a>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                </div>
            `;
        }

        function filterNoticesTable() {
            const query = document.getElementById('notice-filter-input').value;
            const retrieved = searchFDAData(query);
            const container = document.getElementById('notices-list-container');
            const list = retrieved.notices.length > 0 ? retrieved.notices : fdaData.notices;

            container.innerHTML = list.map(n => `
                <div class="p-4 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-3">
                    <div class="space-y-1 max-w-3xl">
                        <div class="flex items-center gap-2">
                            <span class="bg-blue-100 text-blue-800 font-bold px-2 py-0.5 rounded text-[10px]">${n.category}</span>
                            <span class="text-slate-500">${n.date}</span>
                        </div>
                        <h3 class="font-bold text-slate-900">${n.title}</h3>
                    </div>
                    <div class="flex items-center gap-2 flex-shrink-0">
                        <button onclick="openExplainNoticeModal('${n.title}', 'Official notice published under ${n.category}')" class="bg-slate-200 hover:bg-slate-300 text-slate-800 font-bold px-3 py-1.5 rounded">AI Explain</button>
                        <a href="${n.url}" target="_blank" class="bg-govblue-800 text-white font-bold px-3 py-1.5 rounded">Original Link</a>
                    </div>
                </div>
            `).join('');
        }

        /* --- DIRECTORY PAGE --- */
        function renderDirectory() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <div class="max-w-7xl mx-auto px-3 py-6 space-y-6 text-xs">
                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider">FDA & Government Leadership Directory[cite: 1]</h2>
                        <p class="text-slate-600 mt-1">Verified official directory of state government leadership and Maharashtra FDA departmental executives[cite: 1].</p>
                    </div>

                    <div>
                        <h3 class="font-bold text-slate-900 text-sm mb-3 uppercase tracking-wider border-b border-slate-300 pb-1">FDA Departmental Leadership</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            ${fdaData.directory.department.map(person => `
                                <div class="bg-white rounded border border-slate-300 p-4 shadow-xs flex items-center gap-4">
                                    <img src="${person.img}" alt="${person.name}" class="w-16 h-16 rounded object-cover border border-slate-300 flex-shrink-0">
                                    <div>
                                        <span class="bg-blue-100 text-blue-800 font-bold px-2 py-0.5 rounded text-[10px]">${person.role}</span>
                                        <h4 class="font-bold text-slate-900 text-sm mt-1">${person.name}</h4>
                                        <p class="text-slate-600 text-[11px]">${person.desig}</p>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>

                    <div>
                        <h3 class="font-bold text-slate-900 text-sm mb-3 uppercase tracking-wider border-b border-slate-300 pb-1">Government Leadership</h3>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            ${fdaData.directory.leadership.map(person => `
                                <div class="bg-white rounded border border-slate-300 p-4 shadow-xs flex items-center gap-3">
                                    <img src="${person.img}" alt="${person.name}" class="w-14 h-14 rounded object-cover border border-slate-300 flex-shrink-0">
                                    <div>
                                        <span class="bg-slate-100 text-slate-700 font-medium px-2 py-0.5 rounded text-[10px]">${person.role}</span>
                                        <h4 class="font-bold text-slate-900 mt-1">${person.name}</h4>
                                        <p class="text-slate-600 text-[11px]">${person.desig}</p>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                </div>
            `;
        }

        /* --- TRACK COMPLAINT PAGE --- */
        function renderTrackComplaint() {
            const container = document.getElementById('app-container');
            container.innerHTML = `
                <div class="max-w-3xl mx-auto px-3 py-6 space-y-4 text-xs">
                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <h2 class="text-sm font-bold text-govblue-900 uppercase tracking-wider">Complaint Status Tracking</h2>
                        <p class="text-slate-600 mt-1">Enter your Complaint ID (e.g., <span class="font-mono text-blue-700">MHFDA-2026-000001</span>) to check progress.</p>
                    </div>

                    <div class="bg-white rounded border border-slate-300 p-4 shadow-xs">
                        <div class="flex gap-2">
                            <input type="text" id="track-id-input" placeholder="Enter Complaint ID..." class="w-full px-3 py-2 rounded border border-slate-300 text-xs font-mono focus:outline-none focus:border-blue-700">
                            <button onclick="executeComplaintTracking()" class="bg-govblue-800 hover:bg-govblue-900 text-white px-5 py-2 rounded font-bold whitespace-nowrap">
                                Track Status
                            </button>
                        </div>
                        <div class="mt-2 text-[11px] text-slate-500">
                            Demo IDs: <button onclick="document.getElementById('track-id-input').value='MHFDA-2026-000001'; executeComplaintTracking();" class="text-blue-700 underline font-mono">MHFDA-2026-000001</button>, <button onclick="document.getElementById('track-id-input').value='MHFDA-2026-000002'; executeComplaintTracking();" class="text-blue-700 underline font-mono">MHFDA-2026-000002</button>
                        </div>
                    </div>

                    <div id="tracking-result-area"></div>
                </div>
            `;
        }

        function executeComplaintTracking() {
            const id = document.getElementById('track-id-input').value.trim();
            const resultArea = document.getElementById('tracking-result-area');
            if(!id) return;

            const record = complaintsStore.find(c => c.id.toLowerCase() === id.toLowerCase());
            if(!record) {
                resultArea.innerHTML = `<div class="bg-red-50 text-red-800 p-4 rounded border border-red-200 text-xs font-bold">Complaint ID Not Found.</div>`;
                return;
            }

            const steps = ['Complaint Registered', 'AI Analysis Completed', 'Submitted for Officer Review', 'Officer Assigned', 'Investigation / Inspection', 'Resolution'];

            resultArea.innerHTML = `
                <div class="bg-white rounded border border-slate-300 p-5 shadow-xs text-xs space-y-4">
                    <div class="flex justify-between items-center pb-3 border-b border-slate-200">
                        <div>
                            <span class="font-mono font-bold bg-blue-100 text-blue-900 px-2 py-0.5 rounded">${record.id}</span>
                            <h3 class="font-bold text-slate-900 text-sm mt-1">${record.issue}</h3>
                            <p class="text-slate-600 text-[11px]">Category: <strong>${record.category}</strong> | Location: <strong>${record.location}</strong></p>
                        </div>
                        <div class="text-right">
                            <span class="bg-amber-100 text-amber-900 font-bold px-2.5 py-1 rounded text-[10px]">${record.status}</span>
                            <p class="text-[10px] text-slate-500 mt-1">Assigned: ${record.assignedOfficer}</p>
                        </div>
                    </div>

                    <div class="space-y-3 pl-3 border-l-2 border-blue-700">
                        ${steps.map((step, idx) => {
                            const isCompleted = record.history.includes(step) || idx <= 2;
                            return `
                                <div class="relative pl-3">
                                    <div class="absolute -left-[19px] top-0 w-2.5 h-2.5 rounded-full ${isCompleted ? 'bg-blue-700' : 'bg-slate-300'}"></div>
                                    <h4 class="font-bold ${isCompleted ? 'text-slate-900' : 'text-slate-400'}">${step}</h4>
                                </div>
                            `;
                        }).join('')}
                    </div>
                </div>
            `;
        }

        /* --- OFFICER DASHBOARD (Formal Administrative Style) --- */
        function renderOfficerDashboard() {
            const container = document.getElementById('app-container');
            const total = complaintsStore.length + 1240;
            const pending = complaintsStore.filter(c => c.status.includes('Submitted') || c.status.includes('Registered')).length + 138;
            const review = complaintsStore.filter(c => c.status.includes('Review') || c.status.includes('Inspection')).length + 82;
            const highPriority = complaintsStore.filter(c => c.priority.includes('High')).length + 31;
            const resolved = 1021;[cite: 1]

            const totalAiRecs = complaintsStore.length;
            const acceptedRecs = complaintsStore.filter(c => c.officerDecision && c.officerDecision.overrideStatus.includes('Accepted')).length;
            const modifiedRecs = complaintsStore.filter(c => c.officerDecision && c.officerDecision.overrideStatus.includes('Modified')).length;
            const overrideRate = totalAiRecs > 0 ? ((modifiedRecs / totalAiRecs) * 100).toFixed(1) : 0;

            container.innerHTML = `
                <div class="max-w-7xl mx-auto px-3 py-6 space-y-6 text-xs">
                    <div class="bg-govblue-900 text-white p-5 rounded border border-blue-900 shadow-xs flex flex-col md:flex-row justify-between items-start md:items-center gap-3">
                        <div>
                            <h2 class="text-sm font-bold uppercase tracking-wider">FDA Officer Administrative Dashboard</h2>
                            <p class="text-slate-300 text-[11px] mt-0.5">⚠️ Demonstration Data — Not Official FDA Statistics[cite: 1]</p>
                        </div>
                        <div class="bg-blue-950 px-3 py-1.5 rounded border border-blue-800 text-[11px]">
                            <i class="fa-solid fa-user-shield text-amber-400 mr-1"></i> Logged in: <strong>Dr. R. K. Patil (Joint Commissioner)</strong>
                        </div>
                    </div>

                    <!-- Metric Cards -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-3">
                        <div class="bg-white p-4 rounded border border-slate-300 shadow-xs"><span class="text-slate-500">Total Complaints</span><strong class="text-lg text-slate-900 block mt-1">${total}</strong></div>
                        <div class="bg-white p-4 rounded border border-slate-300 shadow-xs"><span class="text-slate-500">Pending Review</span><strong class="text-lg text-amber-700 block mt-1">${pending}</strong></div>
                        <div class="bg-white p-4 rounded border border-slate-300 shadow-xs"><span class="text-slate-500">Under Inspection</span><strong class="text-lg text-blue-800 block mt-1">${review}</strong></div>
                        <div class="bg-white p-4 rounded border border-slate-300 shadow-xs"><span class="text-slate-500">High Priority</span><strong class="text-lg text-orange-700 block mt-1">${highPriority}</strong></div>
                        <div class="bg-white p-4 rounded border border-slate-300 shadow-xs"><span class="text-slate-500">Resolved (YTD)</span><strong class="text-lg text-emerald-700 block mt-1">${resolved}[cite: 1]</strong></div>
                    </div>

                    <!-- AI Routing Analytics Panel -->
                    <div class="bg-white p-4 rounded border border-slate-300 shadow-xs space-y-2">
                        <h3 class="font-bold text-govblue-900 uppercase tracking-wider flex items-center gap-1.5"><i class="fa-solid fa-chart-pie text-blue-700"></i> AI Routing Decision Analytics</h3>
                        <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-slate-700 pt-2">
                            <div class="bg-slate-50 p-2.5 rounded border border-slate-200">Total AI Recs: <strong class="block text-slate-900">${totalAiRecs}</strong></div>
                            <div class="bg-slate-50 p-2.5 rounded border border-slate-200">Officer Accepted: <strong class="block text-emerald-700">${acceptedRecs}</strong></div>
                            <div class="bg-slate-50 p-2.5 rounded border border-slate-200">Officer Modified: <strong class="block text-amber-700">${modifiedRecs}</strong></div>
                            <div class="bg-slate-50 p-2.5 rounded border border-slate-200">Override Rate: <strong class="block text-blue-900">${overrideRate}%</strong></div>
                        </div>
                    </div>

                    <!-- Charts Section -->
                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-4">
                        <div class="bg-white p-4 rounded border border-slate-300 shadow-xs">
                            <h3 class="font-bold text-slate-900 mb-2">Complaints by Category</h3>
                            <div class="h-56 flex items-center justify-center"><canvas id="categoryChart"></canvas></div>
                        </div>
                        <div class="bg-white p-4 rounded border border-slate-300 shadow-xs">
                            <h3 class="font-bold text-slate-900 mb-2">Monthly Complaint Volume (2026)</h3>
                            <div class="h-56 flex items-center justify-center"><canvas id="monthlyChart"></canvas></div>
                        </div>
                    </div>

                    <!-- Complaints Table -->
                    <div class="bg-white rounded border border-slate-300 shadow-xs overflow-hidden">
                        <div class="p-4 bg-slate-50 border-b border-slate-200">
                            <h3 class="font-bold text-slate-900">Incoming Citizen Complaints & Officer Override Controls</h3>
                        </div>
                        <div class="overflow-x-auto">
                            <table class="w-full text-left">
                                <thead class="bg-slate-100 text-slate-700 font-bold uppercase tracking-wider border-b border-slate-300 text-[11px]">
                                    <tr>
                                        <th class="p-3">ID</th>
                                        <th class="p-3">Category</th>
                                        <th class="p-3">Location</th>
                                        <th class="p-3">Priority</th>
                                        <th class="p-3">AI Recommendation</th>
                                        <th class="p-3">Status</th>
                                        <th class="p-3 text-right">Action</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-slate-200">
                                    ${complaintsStore.map(c => `
                                        <tr class="hover:bg-slate-50">
                                            <td class="p-3 font-mono font-bold text-blue-700">${c.id}</td>
                                            <td class="p-3 font-semibold text-slate-900">${c.category}</td>
                                            <td class="p-3 text-slate-600">${c.location}</td>
                                            <td class="p-3 font-semibold ${c.priority.includes('High')?'text-orange-700':''}">${c.priority}</td>
                                            <td class="p-3 text-slate-700">${c.aiAnalysis.issue}</td>
                                            <td class="p-3"><span class="bg-amber-100 text-amber-900 font-bold px-2 py-0.5 rounded text-[10px]">${c.status}</span></td>
                                            <td class="p-3 text-right">
                                                <button onclick="openOfficerActionModal('${c.id}')" class="bg-govblue-800 hover:bg-govblue-900 text-white px-2.5 py-1 rounded font-bold shadow-xs">
                                                    Review & Override
                                                </button>
                                            </td>
                                        </tr>
                                    `).join('')}
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            `;

            setTimeout(() => {
                const drugCount = complaintsStore.filter(c => c.category === 'Drug').length + 54;
                const foodCount = complaintsStore.filter(c => c.category === 'Food').length + 32;
                const cosmeticCount = complaintsStore.filter(c => c.category === 'Cosmetic').length + 10;

                new Chart(document.getElementById('categoryChart').getContext('2d'), {
                    type: 'doughnut',
                    data: {
                        labels: ['Drugs', 'Food', 'Cosmetics'],
                        datasets: [{ data: [drugCount, foodCount, cosmeticCount], backgroundColor: ['#1e40af', '#ea580c', '#3b82f6'] }]
                    },
                    options: { responsive: true, maintainAspectRatio: false }
                });

                new Chart(document.getElementById('monthlyChart').getContext('2d'), {
                    type: 'bar',
                    data: {
                        labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep'],
                        datasets: [{ label: 'Complaints', data: [110, 135, 120, 145, 160, 150, 175, 190, 210], backgroundColor: '#1e40af' }]
                    },
                    options: { responsive: true, maintainAspectRatio: false }
                });
            }, 100);
        }

        function openOfficerActionModal(id) {
            const c = complaintsStore.find(item => item.id === id);
            if(!c) return;
            const similar = findSimilarComplaints(c);

            const modalHTML = `
                <div id="officer-override-modal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-xs z-50 flex items-center justify-center p-3">
                    <div class="bg-white rounded shadow-xl w-full max-w-lg overflow-hidden border border-slate-300 text-xs flex flex-col max-h-[90vh]">
                        <div class="bg-govblue-900 text-white p-3 flex justify-between items-center">
                            <h3 class="font-bold">Officer Review & Override [Complaint ${c.id}]</h3>
                            <button onclick="document.getElementById('officer-override-modal').remove()" class="text-slate-300 hover:text-white"><i class="fa-solid fa-xmark"></i></button>
                        </div>
                        <div class="p-4 space-y-3 overflow-y-auto text-slate-700">
                            <div class="bg-slate-50 p-3 rounded border border-slate-200 space-y-1">
                                <p><strong>Complainant:</strong> ${c.name} (${c.mobile})</p>
                                <p><strong>Description:</strong> ${c.description}</p>
                                <p><strong>AI Classification:</strong> <span class="text-blue-900 font-bold">${c.aiAnalysis.issue}</span></p>
                                <p><strong>Recommended Dept:</strong> <strong class="text-orange-700">${c.aiAnalysis.recommended_department}</strong></p>
                            </div>

                            ${similar.length > 0 ? `
                                <div class="bg-amber-50 p-3 rounded border border-amber-200 space-y-1">
                                    <strong class="text-amber-900 block"><i class="fa-solid fa-triangle-exclamation mr-1"></i> Similar Complaints Detected:</strong>
                                    ${similar.map(s => `<div class="text-[11px] text-amber-800"><strong>${s.id}</strong>: ${s.issue} (${s.location})</div>`).join('')}
                                </div>
                            ` : ''}

                            <div class="space-y-2 pt-2 border-t border-slate-200">
                                <div>
                                    <label class="block font-bold text-slate-700 mb-1">Officer Decision / Action</label>
                                    <select id="ov-action" class="w-full p-2 rounded border border-slate-300 bg-white">
                                        <option value="✓ Accept AI Recommendation">✓ Accept AI Recommendation</option>
                                        <option value="✎ Modify Category/Priority">✎ Modify Category/Priority</option>
                                        <option value="↪ Re-route Department">↪ Re-route Department</option>
                                    </select>
                                </div>
                                <div class="grid grid-cols-2 gap-2">
                                    <div>
                                        <label class="block font-bold text-slate-700 mb-1">Override Category</label>
                                        <select id="ov-cat" class="w-full p-2 rounded border border-slate-300 bg-white">
                                            <option value="Drug" ${c.category==='Drug'?'selected':''}>Drug</option>
                                            <option value="Food" ${c.category==='Food'?'selected':''}>Food</option>
                                            <option value="Cosmetic" ${c.category==='Cosmetic'?'selected':''}>Cosmetic</option>
                                        </select>
                                    </div>
                                    <div>
                                        <label class="block font-bold text-slate-700 mb-1">Override Priority</label>
                                        <select id="ov-priority" class="w-full p-2 rounded border border-slate-300 bg-white">
                                            <option value="High — AI Recommendation">High</option>
                                            <option value="Medium">Medium</option>
                                            <option value="Low">Low</option>
                                        </select>
                                    </div>
                                </div>
                            </div>

                            <div class="pt-3 border-t border-slate-200 flex justify-end gap-2">
                                <button onclick="document.getElementById('officer-override-modal').remove()" class="px-3 py-1.5 bg-slate-200 rounded font-bold text-slate-700">Cancel</button>
                                <button onclick="saveOfficerOverride('${c.id}')" class="px-4 py-1.5 bg-govblue-800 text-white rounded font-bold">Apply Override</button>
                            </div>
                        </div>
                    </div>
                </div>
            `;
            document.body.insertAdjacentHTML('beforeend', modalHTML);
        }

        function saveOfficerOverride(id) {
            const c = complaintsStore.find(item => item.id === id);
            if(c) {
                const action = document.getElementById('ov-action').value;
                c.category = document.getElementById('ov-cat').value;
                c.priority = document.getElementById('ov-priority').value;
                c.status = action.includes('Accept') ? 'Under Review' : 'Investigation / Inspection';
                c.officerDecision = { action, modifiedCategory: c.category, modifiedPriority: c.priority, overrideStatus: action.includes('Accept') ? 'Accepted AI Recommendation' : 'Modified by Officer Override' };
                c.history.push('Officer Override Applied: ' + action);
            }
            document.getElementById('officer-override-modal').remove();
            renderOfficerDashboard();
        }

        function openAiAssistantModal() {
            document.getElementById('ai-assistant-modal').classList.remove('hidden');
            document.getElementById('ai-chat-input').focus();
        }

        function closeAiAssistantModal() {
            document.getElementById('ai-assistant-modal').classList.add('hidden');
        }

        function sendQuickPrompt(text) {
            document.getElementById('ai-chat-input').value = text;
            submitAiChat();
        }

        function renderAiAssistantPage() { renderHome(); openAiAssistantModal(); }

        async function submitAiChat() {
            const inputField = document.getElementById('ai-chat-input');
            const q = inputField.value.trim();
            if(!q) return;

            const chatMessages = document.getElementById('ai-chat-messages');
            chatMessages.innerHTML += `<div class="flex justify-end"><div class="bg-govblue-900 text-white p-2 rounded max-w-[85%]">${q}</div></div>`;
            inputField.value = '';
            chatMessages.scrollTop = chatMessages.scrollHeight;

            const aiResult = await askFDAAI(q);

            setTimeout(() => {
                chatMessages.innerHTML += `
                    <div class="flex items-start gap-2">
                        <div class="w-6 h-6 rounded bg-govblue-900 text-amber-400 flex items-center justify-center flex-shrink-0 font-bold text-[10px]">AI</div>
                        <div class="bg-white p-2.5 rounded border border-slate-200 text-slate-700 max-w-[85%] space-y-1">
                            <p>${aiResult.answer}</p>
                            ${aiResult.source_ids.length > 0 ? `<a href="${aiResult.source_ids[0]}" target="_blank" class="text-blue-700 font-bold hover:underline block text-[10px]">[View Official Portal/Source[cite: 1]]</a>` : ''}
                        </div>
                    </div>
                `;
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }, 400);
        }
    </script>
</body>
</html>
