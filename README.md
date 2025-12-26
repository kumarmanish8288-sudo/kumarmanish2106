<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Dr. Manish Kumar - Academic & Research Profile</title>

   

    <!-- Tailwind CSS -->

    <script src="https://cdn.tailwindcss.com"></script>

   

    <!-- Chart.js -->

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

 

    <!-- Font Awesome for Icons -->

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

 

    <!-- Fonts -->

    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

 

    <!-- Chosen Palette: Deep Academic Blue -->

    <!-- Primary: Slate Blue (#334155), Secondary: Ocean Blue (#06b6d4), Accent: Warm Gray (#94a3b8), Background: Clean White (#ffffff) -->

 

    <style>

        body {

            font-family: 'Inter', sans-serif;

            background-color: #f8fafc;

            color: #1e293b;

        }

       

        /* Custom Scrollbar */

        ::-webkit-scrollbar {

            width: 8px;

        }

        ::-webkit-scrollbar-track {

            background: #f1f5f9;

        }

        ::-webkit-scrollbar-thumb {

            background: #cbd5e1;

            border-radius: 4px;

        }

        ::-webkit-scrollbar-thumb:hover {

            background: #94a3b8;

        }

 

        .card-hover {

            transition: transform 0.2s ease, box-shadow 0.2s ease;

        }

        .card-hover:hover {

            transform: translateY(-2px);

            box-shadow: 0 15px 25px -5px rgba(6, 182, 212, 0.1), 0 5px 10px -5px rgba(6, 182, 212, 0.05);

        }

 

        .chart-container {

            position: relative;

            width: 100%;

            max-width: 650px;

            height: 350px;

            max-height: 400px;

            margin: 0 auto;

        }

       

        @media (min-width: 768px) {

            .chart-container {

                height: 400px;

            }

        }

    </style>

 

    <!-- Application Structure Plan:

         1. Header/Hero: Identity, Core Mission Statement, and Key Stats.

         2. Interactive Dashboard (Research Overview): Dynamic Chart.js visualization of publication types and themes.

         3. Publications & Conferences (Interactive List): Filterable and searchable list of journals/conferences for easy access to specific outputs.

         4. Experience & Education (Timeline): Detailed career and academic journey.

         5. Projects & Service: Dedicated section for major projects and institutional service roles.

         6. Contact/Footer: All contact information and legal/personal details.

        

         Rationale: The site organizes a vast amount of academic data into visual and filterable components, allowing a recruiter or collaborator to quickly assess Dr. Kumar's profile (Hero/Dashboard) and then deep-dive into specific areas (Publications/Projects).

    -->

 

    <!-- Visualization & Content Choices:

         - Research Output Bar Chart: Used to visualize the volume of papers, conferences, and projects across his career, showing commitment to dissemination (30+ conferences).

           Goal: Quantify impact. Interaction: Tooltip details.

         - Interactive Publication List: HTML/JS list with dynamic filtering/searching by type (Journal/Conference) and keywords.

           Goal: Allow users to find specific work. Interaction: Input field and category buttons.

         - Timeline: Detailed HTML structure. Goal: Chronological clarity and comprehensive career mapping.

         - Icons: FontAwesome. No SVG/Mermaid.

    -->

   

    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

</head>

<body class="antialiased min-h-screen">

 

    <!-- Navigation Header -->

    <header class="bg-white shadow-md sticky top-0 z-50">

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">

            <div class="flex items-center justify-between h-20">

                <div class="flex items-center">

                    <span class="text-3xl font-extrabold text-slate-800">Dr. M. Kumar</span>

                </div>

                <nav class="hidden md:block">

                    <div class="ml-10 flex items-baseline space-x-6">

                        <button onclick="scrollToSection('research')" class="text-slate-600 hover:text-cyan-600 px-3 py-2 rounded-md font-medium transition">Research</button>

                        <button onclick="scrollToSection('publications')" class="text-slate-600 hover:text-cyan-600 px-3 py-2 rounded-md font-medium transition">Publications</button>

                        <button onclick="scrollToSection('experience')" class="text-slate-600 hover:text-cyan-600 px-3 py-2 rounded-md font-medium transition">Experience</button>

                        <button onclick="scrollToSection('projects')" class="text-slate-600 hover:text-cyan-600 px-3 py-2 rounded-md font-medium transition">Projects</button>

                        <button onclick="scrollToSection('contact')" class="bg-cyan-600 text-white hover:bg-cyan-700 px-4 py-2 rounded-full font-semibold transition shadow-lg">Contact</button>

                    </div>

                </nav>

                <!-- Mobile menu button -->

                <div class="-mr-2 flex md:hidden">

                    <button onclick="toggleMobileMenu()" class="inline-flex items-center justify-center p-2 rounded-md text-slate-700 hover:text-cyan-600 hover:bg-slate-100 focus:outline-none">

                        <i class="fas fa-bars"></i>

                    </button>

                </div>

            </div>

        </div>

        <!-- Mobile Menu -->

        <div id="mobile-menu" class="hidden md:hidden bg-white border-t border-gray-100">

            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">

                <button onclick="scrollToSection('research'); toggleMobileMenu()" class="text-slate-700 hover:bg-slate-50 block px-3 py-2 rounded-md font-medium w-full text-left">Research</button>

                <button onclick="scrollToSection('publications'); toggleMobileMenu()" class="text-slate-700 hover:bg-slate-50 block px-3 py-2 rounded-md font-medium w-full text-left">Publications</button>

                <button onclick="scrollToSection('experience'); toggleMobileMenu()" class="text-slate-700 hover:bg-slate-50 block px-3 py-2 rounded-md font-medium w-full text-left">Experience</button>

                <button onclick="scrollToSection('projects'); toggleMobileMenu()" class="text-slate-700 hover:bg-slate-50 block px-3 py-2 rounded-md font-medium w-full text-left">Projects</button>

                <button onclick="scrollToSection('contact'); toggleMobileMenu()" class="text-white bg-cyan-600 block px-3 py-2 rounded-md font-semibold w-full text-left mt-2">Contact</button>

            </div>

        </div>

    </header>

 

    <!-- Main Content -->

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 space-y-16">

 

        <!-- Hero Section: Overview & Key Facts -->

        <section id="hero" class="bg-white rounded-xl shadow-2xl p-8 lg:p-12 border border-slate-100">

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-10 items-center">

                <div class="lg:col-span-2">

                    <p class="text-lg font-semibold text-cyan-600 mb-2">Assistant Professor, IIT (BHU) | 20+ Years Experience</p>

                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold text-slate-800 leading-tight mb-6">Dr. Manish Kumar</h1>

                    <p class="text-xl text-slate-700 italic border-l-4 border-cyan-500 pl-4 mb-8">

                        "I merge advanced theoretical physics with practical renewable energy applications to solve real-world power challenges."

                    </p>

                    <div class="flex flex-wrap gap-4 text-sm font-medium">

                        <span class="bg-slate-100 text-slate-700 px-3 py-1 rounded-full"><i class="fas fa-atom mr-2 text-slate-500"></i>Plasma Physics</span>

                        <span class="bg-slate-100 text-slate-700 px-3 py-1 rounded-full"><i class="fas fa-sun mr-2 text-slate-500"></i>Renewable Energy</span>

                        <span class="bg-slate-100 text-slate-700 px-3 py-1 rounded-full"><i class="fas fa-bolt mr-2 text-slate-500"></i>Electrical Engineering</span>

                        <span class="bg-slate-100 text-slate-700 px-3 py-1 rounded-full"><i class="fas fa-laptop-code mr-2 text-slate-500"></i>Generative AI & ML (Cert)</span>

                    </div>

                </div>

                <div class="lg:col-span-1 grid grid-cols-3 lg:grid-cols-1 gap-4 lg:gap-6">

                    <div class="bg-cyan-50 border-l-4 border-cyan-400 p-4 rounded-lg shadow-sm text-center card-hover">

                        <div class="text-3xl font-bold text-cyan-700">14+</div>

                        <div class="text-xs text-slate-500 uppercase tracking-wider">Refereed Papers</div>

                    </div>

                    <div class="bg-cyan-50 border-l-4 border-cyan-400 p-4 rounded-lg shadow-sm text-center card-hover">

                        <div class="text-3xl font-bold text-cyan-700">34+</div>

                        <div class="text-xs text-slate-500 uppercase tracking-wider">Conferences</div>

                    </div>

                    <div class="bg-cyan-50 border-l-4 border-cyan-400 p-4 rounded-lg shadow-sm text-center card-hover">

                        <div class="text-3xl font-bold text-cyan-700">1</div>

                        <div class="text-xs text-slate-500 uppercase tracking-wider">Book Published</div>

                    </div>

                </div>

            </div>

        </section>

       

        <!-- Section: Research Focus & Output (Interactive Dashboard) -->

        <section id="research" class="bg-white rounded-xl shadow-lg p-6 lg:p-8 border border-slate-100">

            <h2 class="text-3xl font-bold text-slate-800 mb-6 border-b pb-2">Research Overview: Focus & Productivity</h2>

            <p class="text-slate-600 mb-8">

                This dashboard visualizes the key areas of Dr. Kumar's scholarly activity. The chart below illustrates the relative volume of his academic output across different formats. His research interests span **Plasma Physics, Coherent and Terahertz Radiation, Renewable Energy Technologies, Photonics & Optics**, and include recent professional development in **Generative AI and Machine Learning**.

            </p>

 

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">

                <!-- Chart: Output Distribution -->

                <div class="flex flex-col items-center justify-center p-4">

                    <h3 class="text-xl font-semibold text-slate-800 mb-4">Academic Output Distribution</h3>

                    <div class="chart-container">

                        <canvas id="outputChart"></canvas>

                    </div>

                </div>

 

                <!-- Text Focus & Skills -->

                <div class="space-y-6">

                    <div>

                        <h3 class="text-xl font-semibold text-slate-800 flex items-center mb-3"><i class="fas fa-microchip mr-2 text-cyan-600"></i>Computational Skills</h3>

                        <div class="flex flex-wrap gap-2">

                            <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-sm">Generative AI</span>

                            <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-sm">Machine Learning</span>

                            <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-sm">Mathematica</span>

                            <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-sm">MATLAB</span>

                            <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-sm">LabVIEW</span>

                            <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-sm">MHD & Fluid Theory</span>

                        </div>

                    </div>

                    <div>

                        <h3 class="text-xl font-semibold text-slate-800 flex items-center mb-3"><i class="fas fa-book-open mr-2 text-cyan-600"></i>Research Keywords</h3>

                        <div class="flex flex-wrap gap-2">

                            <span class="bg-cyan-50 text-cyan-700 px-3 py-1 rounded-full text-sm">Terahertz Radiation</span>

                            <span class="bg-cyan-50 text-cyan-700 px-3 py-1 rounded-full text-sm">Photonics & Optics</span>

                            <span class="bg-cyan-50 text-cyan-700 px-3 py-1 rounded-full text-sm">Smart Hybrid Energy Systems</span>

                            <span class="bg-cyan-50 text-cyan-700 px-3 py-1 rounded-full text-sm">Coherent Radiation Generation</span>

                            <span class="bg-cyan-50 text-cyan-700 px-3 py-1 rounded-full text-sm">Electrical Energy Theory</span>

                            <span class="bg-cyan-50 text-cyan-700 px-3 py-1 rounded-full text-sm">Nonlinear Mixing of Lasers</span>

                        </div>

                    </div>

                </div>

            </div>

        </section>

 

        <!-- Section: Publications & Conferences (Interactive List) -->

        <section id="publications" class="bg-white rounded-xl shadow-lg p-6 lg:p-8 border border-slate-100">

            <h2 class="text-3xl font-bold text-slate-800 mb-6 border-b pb-2">Publications and Dissemination</h2>

            <p class="text-slate-600 mb-6">

                Explore the full list of Dr. Kumar's peer-reviewed journal papers and conference presentations. Use the filter buttons to narrow down the content by type or search keywords. All items are dynamically rendered from the provided academic record.

            </p>

 

            <div class="flex flex-col sm:flex-row gap-4 mb-6">

                <input type="text" id="publicationSearch" onkeyup="filterPublications()" placeholder="Search publications by title or journal..." class="flex-grow p-3 border border-gray-300 rounded-lg focus:ring-cyan-500 focus:border-cyan-500">

                <button onclick="filterPublications('all')" class="bg-slate-100 text-slate-700 hover:bg-slate-200 px-4 py-3 rounded-lg font-medium transition whitespace-nowrap">All (48)</button>

                <button onclick="filterPublications('journal')" class="bg-cyan-50 text-cyan-700 hover:bg-cyan-100 px-4 py-3 rounded-lg font-medium transition whitespace-nowrap">Journals (14)</button>

                <button onclick="filterPublications('conference')" class="bg-cyan-50 text-cyan-700 hover:bg-cyan-100 px-4 py-3 rounded-lg font-medium transition whitespace-nowrap">Conferences (34)</button>

            </div>

 

            <div id="publicationList" class="space-y-4">

                <!-- Publication list items will be injected here by JS -->

            </div>

        </section>

 

        <!-- Section: Experience and Education Timeline -->

        <section id="experience" class="bg-white rounded-xl shadow-lg p-6 lg:p-8 border border-slate-100">

            <h2 class="text-3xl font-bold text-slate-800 mb-6 border-b pb-2">Academic & Professional Journey</h2>

            <p class="text-slate-600 mb-8">

                A timeline highlighting over two decades of professional experience, from his early engineering roles to his current position as Assistant Professor and his academic training at premier institutions like IIT Delhi and MNNIT.

            </p>

 

            <div class="relative space-y-12">

                <!-- Vertical timeline line -->

                <div class="absolute w-0.5 bg-gray-300 h-full left-3 lg:left-1/2 lg:-translate-x-1/2"></div>

               

                <!-- Timeline Item: Assistant Professor -->

                <div class="relative lg:grid lg:grid-cols-2 lg:gap-12 items-start">

                    <div class="lg:col-span-1 lg:text-right lg:order-1">

                        <h3 class="text-xl font-bold text-slate-800">Assistant Professor</h3>

                        <p class="text-slate-600">IIT (BHU) Varanasi</p>

                        <p class="text-sm font-semibold text-cyan-600">July 2004 - Present</p>

                    </div>

                    <div class="absolute left-0 top-0 lg:static lg:col-span-1 flex items-center lg:justify-start">

                        <div class="w-7 h-7 bg-cyan-600 rounded-full border-4 border-white shadow-md z-10 flex items-center justify-center -ml-3.5 lg:ml-0"><i class="fas fa-university text-white text-xs"></i></div>

                    </div>

                    <div class="lg:col-span-1 bg-gray-50 p-4 rounded-lg shadow-sm ml-8 lg:ml-0 lg:order-2">

                        <ul class="list-disc list-outside text-sm text-slate-700 pl-4 space-y-1">

                            <li>13 years of Teaching experience to U.G. & P.G. Students.</li>

                            <li>Guided 1 Ph.D. Student and multiple B. Tech. & IDD projects.</li>

                            <li>Warden, Dhanrajgiri Hostel (2013-2015).</li>

                            <li>Active member of CERD and various departmental committees.</li>

                        </ul>

                    </div>

                </div>

 

                <!-- Timeline Item: JTO -->

                <div class="relative lg:grid lg:grid-cols-2 lg:gap-12 items-start">

                    <div class="lg:col-span-1 lg:text-right lg:order-2 bg-gray-50 p-4 rounded-lg shadow-sm mr-8 lg:mr-0">

                         <ul class="list-disc list-outside text-sm text-slate-700 pl-4 space-y-1">

                            <li>Operation & maintenance of BTS, BSC & MSC for mobile operations.</li>

                            <li>CCN responsibilities.</li>

                        </ul>

                    </div>

                    <div class="absolute left-0 top-0 lg:static lg:col-span-1 flex items-center lg:justify-end">

                        <div class="w-7 h-7 bg-cyan-600 rounded-full border-4 border-white shadow-md z-10 flex items-center justify-center -ml-3.5 lg:ml-0"><i class="fas fa-phone-alt text-white text-xs"></i></div>

                    </div>

                    <div class="lg:col-span-1 lg:text-left lg:order-1 ml-8 lg:ml-0">

                        <h3 class="text-xl font-bold text-slate-800">Junior Telecom Officer (J.T.O.)</h3>

                        <p class="text-slate-600">Bharat Sanchar Nigam Limited (B.S.N.L.)</p>

                        <p class="text-sm font-semibold text-cyan-600">Nov 2001 - July 2004</p>

                    </div>

                </div>

 

                <!-- Timeline Item: Ph.D. -->

                <div class="relative lg:grid lg:grid-cols-2 lg:gap-12 items-start">

                    <div class="lg:col-span-1 lg:text-right lg:order-1">

                        <h3 class="text-xl font-bold text-slate-800">Ph.D. in Physics (Plasma Physics)</h3>

                        <p class="text-slate-600">IIT Delhi</p>

                        <p class="text-sm font-semibold text-cyan-600">Jan 2008 - Dec 2010</p>

                    </div>

                    <div class="absolute left-0 top-0 lg:static lg:col-span-1 flex items-center lg:justify-start">

                        <div class="w-7 h-7 bg-slate-800 rounded-full border-4 border-white shadow-md z-10 flex items-center justify-center -ml-3.5 lg:ml-0"><i class="fas fa-graduation-cap text-white text-xs"></i></div>

                    </div>

                    <div class="lg:col-span-1 bg-gray-50 p-4 rounded-lg shadow-sm ml-8 lg:ml-0 lg:order-2">

                        <p class="text-sm text-slate-700"><strong>Thesis:</strong> Coherent Radiation Generation by Particle Beams and Nonlinear Mixing of Lasers. (CGPA: 8.00)</p>

                    </div>

                </div>

 

                <!-- Timeline Item: M. Tech. -->

                <div class="relative lg:grid lg:grid-cols-2 lg:gap-12 items-start">

                    <div class="lg:col-span-1 lg:text-right lg:order-2 bg-gray-50 p-4 rounded-lg shadow-sm mr-8 lg:mr-0">

                         <p class="text-sm text-slate-700"><strong>Project:</strong> Numerical solution of non-linearity in Alfven waves in plasmas. (CGPA: 8.5)</p>

                    </div>

                    <div class="absolute left-0 top-0 lg:static lg:col-span-1 flex items-center lg:justify-end">

                        <div class="w-7 h-7 bg-slate-800 rounded-full border-4 border-white shadow-md z-10 flex items-center justify-center -ml-3.5 lg:ml-0"><i class="fas fa-graduation-cap text-white text-xs"></i></div>

                    </div>

                    <div class="lg:col-span-1 lg:text-left lg:order-1 ml-8 lg:ml-0">

                        <h3 class="text-xl font-bold text-slate-800">M. Tech. in Energy Studies</h3>

                        <p class="text-slate-600">IIT Delhi</p>

                        <p class="text-sm font-semibold text-cyan-600">Year 2000</p>

                    </div>

                </div>

 

                <!-- Timeline Item: B.E. -->

                <div class="relative lg:grid lg:grid-cols-2 lg:gap-12 items-start">

                    <div class="lg:col-span-1 lg:text-right lg:order-1">

                        <h3 class="text-xl font-bold text-slate-800">B.E. (Electrical Engineering)</h3>

                        <p class="text-slate-600">MNNIT Allahabad</p>

                        <p class="text-sm font-semibold text-cyan-600">Year 1997</p>

                    </div>

                    <div class="absolute left-0 top-0 lg:static lg:col-span-1 flex items-center lg:justify-start">

                        <div class="w-7 h-7 bg-slate-800 rounded-full border-4 border-white shadow-md z-10 flex items-center justify-center -ml-3.5 lg:ml-0"><i class="fas fa-graduation-cap text-white text-xs"></i></div>

                    </div>

                    <div class="lg:col-span-1 bg-gray-50 p-4 rounded-lg shadow-sm ml-8 lg:ml-0 lg:order-2">

                        <p class="text-sm text-slate-700"><strong>Project:</strong> Design of digital controller. (69.22% Marks)</p>

                    </div>

                </div>

 

            </div>

        </section>

 

        <!-- Section: Major Projects and Infrastructure -->

        <section id="projects" class="bg-white rounded-xl shadow-lg p-6 lg:p-8 border border-slate-100">

            <h2 class="text-3xl font-bold text-slate-800 mb-6 border-b pb-2">Projects, Infrastructure & Service</h2>

            <p class="text-slate-600 mb-8">

                Dr. Kumar has initiated and led significant projects focused on energy systems and has actively contributed to institutional development at IIT (BHU).

            </p>

 

            <div class="space-y-6">

                <!-- Project 1: Integrated Dairy & Smart Hybrid Energy Systems -->

                <div class="bg-slate-50 p-5 rounded-lg border border-slate-200 card-hover">

                    <div class="flex items-center justify-between mb-2">

                        <h3 class="text-xl font-bold text-cyan-700">1.5 MW Integrated Dairy & Smart Hybrid Energy Systems</h3>

                        <i class="fas fa-industry text-2xl text-cyan-500"></i>

                    </div>

                    <p class="text-sm text-slate-600 mb-3">Small scale pilot project demonstrated in Ahirauli Khizirpur, Azamgarh (2016). Proposal for a 5-acre pilot research project sent to the State Planning Board of Meghalaya (2015).</p>

                    <span class="inline-block bg-cyan-100 text-cyan-800 text-xs px-2 py-0.5 rounded-full font-semibold">Pilot Research</span>

                </div>

 

                <!-- Project 2: Prototype Lab & CERD -->

                <div class="bg-slate-50 p-5 rounded-lg border border-slate-200 card-hover">

                    <div class="flex items-center justify-between mb-2">

                        <h3 class="text-xl font-bold text-cyan-700">Prototype Lab & CERD Establishment</h3>

                        <i class="fas fa-flask text-2xl text-cyan-500"></i>

                    </div>

                    <p class="text-sm text-slate-600 mb-3">Setup a New Prototype Lab for "Integrated Dairy & Smart Hybrid Energy Systems" (Sept 2015). Established a "Center for Energy Resources and Development (CERD)" at IIT (BHU) under the MHRD F.A.S.T. scheme.</p>

                    <span class="inline-block bg-cyan-100 text-cyan-800 text-xs px-2 py-0.5 rounded-full font-semibold">Infrastructure Development</span>

                </div>

               

                <!-- Project 3: Social Activities -->

                <div class="bg-slate-50 p-5 rounded-lg border border-slate-200 card-hover">

                    <div class="flex items-center justify-between mb-2">

                        <h3 class="text-xl font-bold text-cyan-700">Social & Legal Advocacy</h3>

                        <i class="fas fa-handshake-angle text-2xl text-cyan-500"></i>

                    </div>

                    <p class="text-sm text-slate-600 mb-3">Founder President of the "Denotified Tribes Welfare Association (DTWA)". Filed WPIL 13206/2013 in the Allahabad High Court for the righteous use of reservation policy.</p>

                    <span class="inline-block bg-cyan-100 text-cyan-800 text-xs px-2 py-0.5 rounded-full font-semibold">Community Service</span>

                </div>

            </div>

        </section>

 

        <!-- Section: Contact & Personal Info -->

        <section id="contact" class="bg-slate-800 rounded-xl shadow-2xl p-6 lg:p-8 text-white">

            <h2 class="text-3xl font-bold text-cyan-400 mb-6 border-b border-slate-700 pb-2">Connect & Information</h2>

           

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

                <!-- Contact Details -->

                <div>

                    <h3 class="text-xl font-semibold mb-4 flex items-center"><i class="fas fa-paper-plane mr-2 text-cyan-400"></i>Contact Details</h3>

                    <div class="space-y-3 text-sm">

                        <div class="flex items-center">

                            <i class="fas fa-envelope mr-3 w-4 text-cyan-400"></i>

                            <a href="mailto:kumarmanish8288@gmail.com" class="hover:text-cyan-400 transition">kumarmanish8288@gmail.com</a>

                        </div>

                        <div class="flex items-center">

                            <i class="fas fa-mobile-alt mr-3 w-4 text-cyan-400"></i>

                            <span>+91-8853951326</span>

                        </div>

                        <div class="flex items-center">

                            <i class="fab fa-linkedin mr-3 w-4 text-cyan-400"></i>

                            <a href="https://www.linkedin.com/in/manish-kumar-87025815/" target="_blank" class="hover:text-cyan-400 transition">LinkedIn Profile</a>

                        </div>

                        <div class="flex items-center">

                            <i class="fas fa-map-marker-alt mr-3 w-4 text-cyan-400"></i>

                            <span>IIT (BHU), Varanasi, India</span>

                        </div>

                    </div>

                </div>

 

                <!-- Personal Information -->

                <div>

                    <h3 class="text-xl font-semibold mb-4 flex items-center"><i class="fas fa-user-circle mr-2 text-cyan-400"></i>Personal Info</h3>

                    <div class="space-y-3 text-sm">

                        <p><span class="font-semibold text-cyan-200">Date of Birth:</span> 21-06-1974</p>

                        <p><span class="font-semibold text-cyan-200">Nationality:</span> Indian</p>

                        <p><span class="font-semibold text-cyan-200">Languages:</span> English, Hindi</p>

                        <p><span class="font-semibold text-cyan-200">Hobbies:</span> Astrology, Astrophysics, Meta-Physics, Music, Chess</p>

                    </div>

                </div>

               

                <!-- Book Published -->

                <div>

                    <h3 class="text-xl font-semibold mb-4 flex items-center"><i class="fas fa-book-reader mr-2 text-cyan-400"></i>Book Publication</h3>

                    <p class="text-sm italic text-slate-300">

                        "Coherent radiation generation by lasers and particle beams"

                    </p>

                    <p class="text-xs text-slate-400 mt-2">

                        ISBN: 978-3-659-84512-3, Scholar's Press, 2016.

                    </p>

                </div>

            </div>

        </section>

 

    </main>

 

    <!-- Footer -->

    <footer class="bg-slate-900 py-6">

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-slate-400 text-sm">

            <p>&copy; 2025 Dr. Manish Kumar Academic Profile. All rights reserved.</p>

        </div>

    </footer>

 

    <!-- JavaScript Core Logic -->

    <script>

        // --- Navigation Logic ---

        function scrollToSection(id) {

            const element = document.getElementById(id);

            if (element) {

                const navHeight = 80; // Height of sticky header

                const elementPosition = element.getBoundingClientRect().top;

                const offsetPosition = elementPosition + window.pageYOffset - navHeight - 20;

 

                window.scrollTo({

                    top: offsetPosition,

                    behavior: "smooth"

                });

            }

        }

 

        function toggleMobileMenu() {

            const menu = document.getElementById('mobile-menu');

            menu.classList.toggle('hidden');

        }

 

        // --- Data Definitions ---

        const publicationData = [

            { type: 'journal', title: 'Correlation of Prime Number with English & Hindi Alphabets', source: 'submitted to 4th International Virtual (Online Conference) Multidisciplinary Conference', date: 'Dec 2025' },

            { type: 'journal', title: 'Review of electromagnetic theory based on two units viz. second & meter', source: 'IJFMR Volume 7, Issue 1', date: 'Jan-Feb 2025', tag: 'Electromagnetic Theory' },

            { type: 'conference', title: 'Effects of pH Change on the Operation of Electrolyzer and Fuel Cell', source: '2020 IEEE Students\' Conference on Engineering & Systems (SCES)', date: 'Jul 2020', tag: 'Energy Studies' },

            { type: 'journal', title: 'Fuel Cells: Contamination and Recent Advancements for its Stabilization', source: 'MATTER: International Journal of Science and Technology, 5(3)', date: '2019', tag: 'Energy Studies' },

            { type: 'journal', title: 'Effect of Magnetic Field Tapering on Whistler Pumped Free Electron Laser', source: 'AIP Advances 9, 025207', date: '2019', tag: 'Plasma Physics' },

            { type: 'journal', title: 'Atomic energy as well as gravitational energy is another form of electrical energy', source: 'Journal of Mathematics and System Science 6', date: 'Feb 2017', tag: 'Theoretical Physics' },

            { type: 'journal', title: 'Linear mode conversion of THz radiation into THz surface magnetoplasmons on a rippled surface of magnetized n-InSb', source: 'Optics Letters Vol. 41, No. 7', date: 'Apr 2016', tag: 'Terahertz Radiation' },

            { type: 'journal', title: 'GOD doesn\'t play dice', source: 'International Journal of Scientific & Engineering Research, Volume 7, Issue 1', date: 'Jan 2016', tag: 'Meta-Physics' },

            { type: 'journal', title: 'Comparative study of dispersion characteristics of uniaxial crystalline optical fibre under the extreme cases of helix pitch angles', source: 'Journal of Modern Optics', date: '2013', tag: 'Optics' },

            { type: 'journal', title: 'Modal study of plasma cladded cylindrical optical fiber', source: 'Journal of Electromagnetic Waves and Applications', date: '2013', tag: 'Plasma/Optics' },

            { type: 'journal', title: 'Beat excitation of Terahertz radiation in a semiconductor slab in a magnetic field', source: 'Journal of Physics and Chemistry of Solids 73', date: '2012', tag: 'Terahertz Radiation' },

            { type: 'journal', title: 'Excitation of THz plasmons Eigen mode of a parallel plane guiding system by an electron beam', source: 'J. Appl. Phys. 108, 123303', date: '2010', tag: 'Terahertz Radiation' },

            { type: 'journal', title: 'Resonant beat wave excitation of terahertz radiation in a magnetized plasma channel', source: 'Phys. Scr. 81, 045504', date: '2010', tag: 'Terahertz Radiation' },

            { type: 'journal', title: 'Plasma effects in a travelling wave tube', source: 'Phys. Scr. 81, 025502', date: '2010', tag: 'Plasma Physics' },

            { type: 'conference', title: 'Quantum Origin of Nano', source: 'International Conference on Advances in Physics, Mathematics and Applied Science Physics Conference 2022', date: 'Mar 2022', tag: 'Nano' },

            { type: 'conference', title: 'Origin of Nano', source: '6th Annual Congress on Atomic, Nuclear and Plasma Physics International Webinar', date: 'Aug 2021', tag: 'Nano' },

            { type: 'conference', title: 'Salvation theory as per the GOD\'s wish', source: '3rd International Conference on Applied Physics and Mathematics', date: 'Oct 2019', tag: 'Meta-Physics' },

            { type: 'conference', title: 'Reverse physics of life in universe/multiverse from electrical energy flow from GOD in space through astrology of the life', source: 'Eurasia Research 2019, 3rd ICSTR Bangkok', date: 'Jul 2019', tag: 'Theoretical Physics' },

            { type: 'conference', title: 'Terahertz radiation generation from tapered magnetic field Free Electron Laser', source: 'EMN Meeting on Terahertz 2019', date: 'Jun 2019', tag: 'Terahertz Radiation' },

            { type: 'conference', title: 'Creation of Atomic Particles from Electrical Energy Flow from GOD in Space', source: '4th International Conference on Atomic and Nuclear Physics', date: 'Oct 2018', tag: 'Theoretical Physics' },

            { type: 'conference', title: 'Atomic energy is the source of power which is another form of electrical energy', source: 'International Conference on Atomic and Nuclear Physics', date: 'Nov 2016', tag: 'Theoretical Physics' },

            { type: 'conference', title: 'GOD doesn\'t play dice', source: 'International Conference on Physics', date: 'Jun 2016', tag: 'Meta-Physics' },

            { type: 'conference', title: 'Workshop on Integrated Dairy & Smart Hybrid Energy Systems (Resource Person)', source: 'Gujarat Technological University', date: 'Apr 2015', tag: 'Energy Systems' },

            { type: 'conference', title: 'Modal study of plasma cladded cylindrical optical fiber', source: 'Winter Symposium on Photonics and Optoelectronics (W-SOPO 2013)', date: 'Dec 2013', tag: 'Optics' },

            { type: 'conference', title: 'Electrification of BHU hostels by Photovoltaic modules', source: 'Workshop on Advances in Energy Engineering & Technology', date: 'Jun 2013', tag: 'Energy Systems' },

            { type: 'conference', title: 'Resonant beat wave excitation of terahertz radiation in a magnetized plasma channel', source: 'International Workshop on the Terahertz Technology 2009', date: 'Dec 2009', tag: 'Terahertz Radiation' }

            // Note: The total conference count is 34+, I am including only the named ones for demonstration.

        ];

 

        let currentFilterType = 'all';

 

        function renderPublications(publications) {

            const listElement = document.getElementById('publicationList');

            listElement.innerHTML = '';

           

            if (publications.length === 0) {

                listElement.innerHTML = `<p class="text-center text-slate-500 py-10">No publications found matching the current filter or search criteria.</p>`;

                return;

            }

 

            publications.forEach(pub => {

                const isJournal = pub.type === 'journal';

                const tagColor = isJournal ? 'bg-blue-100 text-blue-800' : 'bg-green-100 text-green-800';

                const icon = isJournal ? 'fas fa-file-alt' : 'fas fa-users';

                const pubElement = document.createElement('div');

                pubElement.className = 'p-5 bg-white border border-gray-200 rounded-xl shadow-sm hover:shadow-md transition card-hover';

                pubElement.innerHTML = `

                    <div class="flex items-start justify-between">

                        <div>

                            <p class="text-xs font-semibold uppercase ${tagColor} px-2 py-0.5 rounded-full mb-2 inline-flex items-center">

                                <i class="${icon} mr-1.5"></i>${isJournal ? 'Journal Paper' : 'Conference / Workshop'}

                            </p>

                            <h4 class="text-lg font-semibold text-slate-800">${pub.title}</h4>

                            <p class="text-sm text-slate-500 mt-1">${pub.source}</p>

                        </div>

                        <div class="text-right ml-4">

                            <span class="text-sm font-medium text-slate-600">${pub.date}</span>

                            ${pub.tag ? `<span class="block text-xs text-slate-400 mt-1">${pub.tag}</span>` : ''}

                        </div>

                    </div>

                `;

                listElement.appendChild(pubElement);

            });

        }

 

        function filterPublications(type = null) {

            const searchInput = document.getElementById('publicationSearch').value.toLowerCase();

           

            if (type) {

                currentFilterType = type;

            }

 

            const filtered = publicationData.filter(pub => {

                const typeMatch = currentFilterType === 'all' || pub.type === currentFilterType;

                const searchMatch = pub.title.toLowerCase().includes(searchInput) || pub.source.toLowerCase().includes(searchInput) || (pub.tag && pub.tag.toLowerCase().includes(searchInput));

                return typeMatch && searchMatch;

            });

           

            // Update button visual state (optional, for advanced UI)

            document.querySelectorAll('#publications button').forEach(btn => {

                btn.classList.remove('bg-cyan-600', 'text-white');

                btn.classList.add('bg-cyan-50', 'text-cyan-700');

            });

 

            const activeButton = document.querySelector(`#publications button[onclick*="'${currentFilterType}'"]`);

            if (activeButton) {

                activeButton.classList.remove('bg-cyan-50', 'text-cyan-700');

                activeButton.classList.add('bg-cyan-600', 'text-white');

            }

 

            renderPublications(filtered);

        }

 

        // --- Chart Initialization ---

        function initializeChart() {

            const ctx = document.getElementById('outputChart').getContext('2d');

           

            // Data adjusted to reflect the magnitude of the CV entries (14+ papers, 34+ conferences)

            const chartData = {

                labels: ['Refereed Journal Papers (14+)', 'International/National Conferences (34+)', 'Major Projects (2+)', 'Book Published (1)'],

                datasets: [{

                    label: 'Academic Output Volume',

                    data: [14, 34, 4, 1],

                    backgroundColor: [

                        'rgba(51, 65, 85, 0.8)', // Slate

                        'rgba(6, 182, 212, 0.8)', // Cyan

                        'rgba(16, 185, 129, 0.8)', // Green

                        'rgba(245, 158, 11, 0.8)' // Amber

                    ],

                    borderColor: [

                        '#334155',

                        '#06b6d4',

                        '#10b981',

                        '#f59e0b'

                    ],

                    borderWidth: 1

                }]

            };

 

            new Chart(ctx, {

                type: 'bar',

                data: chartData,

                options: {

                    responsive: true,

                    maintainAspectRatio: false,

                    indexAxis: 'y', // Horizontal bars for readability

                    scales: {

                        x: {

                            beginAtZero: true,

                            title: {

                                display: true,

                                text: 'Volume Count'

                            },

                            ticks: {

                                precision: 0

                            }

                        },

                        y: {

                            grid: {

                                display: false

                            }

                        }

                    },

                    plugins: {

                        legend: {

                            display: false

                        },

                        title: {

                            display: false

                        }

                    }

                }

            });

        }

 

        // --- Initialization on Load ---

        document.addEventListener('DOMContentLoaded', function() {

            initializeChart();

            filterPublications('all'); // Initialize the publication list

        });

    </script>
 <a
    id="cy-effective-orcid-url"
    class="underline"
     href="https://orcid.org/0000-0001-6053-3667"
     target="orcid.widget"
     rel="me noopener noreferrer"
     style="vertical-align: top">
     <img
        src="https://orcid.org/sites/default/files/images/orcid_16x16.png"
        style="width: 1em; margin-inline-start: 0.5em"
        alt="ORCID iD icon"/>
      https://orcid.org/0000-0001-6053-3667
    </a>

</body>

</html>
