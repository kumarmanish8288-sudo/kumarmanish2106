<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dr. Manish Kumar | Assistant Professor, IIT (BHU) Varanasi | ORCID 0000-0001-6053-3667</title>
  
  <!-- jQuery + DataTables for publications -->
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <link rel="stylesheet" href="https://cdn.datatables.net/1.13.8/css/jquery.dataTables.min.css">
  <script src="https://cdn.datatables.net/1.13.8/js/jquery.dataTables.min.js"></script>
  
  <!-- bib-publication-list -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/vkaravir/bib-publication-list@master/bib-publication-list.css">
  <script src="https://cdn.jsdelivr.net/gh/vkaravir/bib-publication-list@master/bib-list-min.js"></script>
  
  <!-- ORCID Badge CSS -->
  <link rel="stylesheet" href="https://orcid.org/sites/default/files/modules/orcid-angular-client/build/orcid.css">
  
  <style>
    :root {
      --primary: #3498db;
      --secondary: #2c3e50;
      --accent: #e74c3c;
      --light: #ecf0f1;
      --dark: #34495e;
      --shadow: 0 4px 12px rgba(0,0,0,0.15);
      --orcid-blue: #A6CE39;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { 
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; 
      line-height: 1.6; color: var(--dark);
      background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
    }

    .container { max-width: 1200px; margin: 0 auto; padding: 0 1rem; }

    /* Header */
    header { 
      background: white; 
      box-shadow: var(--shadow);
      position: sticky; top: 0; z-index: 100;
    }
    .header-content { 
      display: flex; justify-content: space-between; align-items: center; 
      padding: 1rem 0; 
    }
    .logo h1 { 
      color: var(--secondary); font-size: 1.8rem; 
      font-weight: 700; 
    }
    .header-info { 
      text-align: right; 
    }
    .tagline { 
      color: var(--primary); font-size: 0.95rem; font-weight: 500; margin-bottom: 0.25rem;
    }
    .orcid-badge {
      display: inline-flex; align-items: center; gap: 0.5rem; font-size: 0.9rem;
      color: var(--orcid-blue); font-weight: 600; text-decoration: none;
    }
    .orcid-badge:hover { color: #88b01a; }
    .orcid-icon {
      width: 18px; height: 18px; background: var(--orcid-blue);
      mask: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 256 256"><path fill="%23FFFFFF" d="M234.459 56.276c-6.447-25.035-24.451-44.44-49.599-50.371a50.804 50.804 0 0 0-6.804-1.064V2.319C178.056.847 177.203 0 176.156 0h-96.288c-1.047 0-1.9.847-1.9 1.894v2.52a50.804 50.804 0 0 0-6.804 1.064c-25.148 5.931-43.152 25.336-49.599 50.371C7.195 81.635 0 106.392 0 132.564c0 27.807 8.013 53.859 21.982 75.44 1.748 2.722 3.49 5.385 5.228 8.021l30.037 59.997c3.337 6.668 10.376 10.555 17.98 10.555 2.119 0 4.255-.328 6.329-.976l37.493-11.221c4.19-1.253 8.759-1.253 12.949 0l37.493 11.221c2.074.748 4.21 1.076 6.329.976 7.604 0 14.643-3.887 17.98-10.555l30.037-59.997c1.738-2.636 3.48-5.299 5.228-8.021 13.969-21.581 21.982-47.633 21.982-75.44 0-26.172-7.195-50.929-19.523-76.288ZM128 33.532a10.667 10.667 0 1 1 0-21.334 10.667 10.667 0 0 1 0 21.334Zm64 99.072h-32v64h-32v-64H96v64H64v-64H32v64H0v-64H32v-32h64v-32h32v32h64v32h32v64h-32v-64Zm0-32h-64v32h64v-32Z"/></svg>') no-repeat center;
      mask-size: contain;
    }
    
    nav a { 
      color: var(--dark); text-decoration: none; margin-left: 2rem; 
      font-weight: 500; transition: color 0.3s;
    }
    nav a:hover, nav a.active { color: var(--primary); }

    /* Hero */
    .hero { 
      text-align: center; padding: 4rem 0; background: white; margin-bottom: 3rem;
      box-shadow: var(--shadow);
    }
    .hero h2 { 
      font-size: 2.5rem; color: var(--secondary); margin-bottom: 1rem; 
    }
    .hero p { 
      font-size: 1.3rem; color: #7f8c8d; max-width: 600px; margin: 0 auto 1.5rem;
      font-style: italic;
    }
    .hero-links {
      display: flex; gap: 1.5rem; justify-content: center; align-items: center;
      flex-wrap: wrap;
    }

    /* Section */
    section { 
      background: white; margin-bottom: 3rem; border-radius: 12px; 
      padding: 2.5rem; box-shadow: var(--shadow);
    }
    section h2 { 
      color: var(--secondary); font-size: 1.8rem; margin-bottom: 1.5rem;
      border-bottom: 3px solid var(--primary); padding-bottom: 0.5rem;
      display: flex; align-items: center; gap: 0.75rem;
    }

    /* Responsive Gallery */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }
    .gallery-item {
      position: relative; overflow: hidden; border-radius: 12px;
      box-shadow: var(--shadow); transition: transform 0.3s;
    }
    .gallery-item:hover { transform: translateY(-5px); }
    .gallery-item img {
      width: 100%; height: 220px; object-fit: cover; transition: transform 0.3s;
    }
    .gallery-item:hover img { transform: scale(1.05); }
    .gallery-item figcaption {
      padding: 1rem; background: white; text-align: center;
      font-weight: 500; color: var(--dark);
    }

    /* Publications Table */
    #pubTable_wrapper { margin-top: 2rem; }
    #pubTable { font-size: 0.92rem; width: 100% !important; }
    .dataTables_wrapper .dataTables_length,
    .dataTables_wrapper .dataTables_filter { margin-bottom: 1rem; }
    .doi-link a { color: var(--primary); text-decoration: none; }
    .doi-link a:hover { text-decoration: underline; }
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

    /* Timeline */
    .timeline {
      position: relative; padding-left: 2rem; max-width: 800px; margin: 0 auto;
    }
    .timeline::before {
      content: ''; position: absolute; left: 0; top: 0; bottom: 0;
      width: 2px; background: var(--primary);
    }
    .timeline-item {
      position: relative; margin-bottom: 2.5rem; padding-left: 2rem;
    }
    .timeline-item::before {
      content: ''; position: absolute; left: -34px; top: 0.5rem;
      width: 12px; height: 12px; background: var(--primary);
      border-radius: 50%; box-shadow: 0 0 0 3px white;
    }
    .timeline-date { 
      font-weight: 700; color: var(--primary); font-size: 0.95rem; 
    }
    .timeline-title { 
      font-size: 1.2rem; color: var(--secondary); margin: 0.25rem 0; 
    }

    /* Projects */
    .projects-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
    }
    .project-card {
      background: var(--light); padding: 1.5rem; border-radius: 8px;
      border-left: 4px solid var(--primary);
    }

    /* Contact */
    .contact-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
    }

    /* Footer */
    footer { 
      background: var(--secondary); color: white; text-align: center;
      padding: 2rem 0; margin-top: 3rem;
    }
    footer a { color: var(--primary); text-decoration: none; }

    /* Responsive */
    @media (max-width: 768px) {
      .header-content { flex-direction: column; gap: 1rem; text-align: center; }
      nav a { margin: 0 1rem; }
      .hero h2 { font-size: 2rem; }
      section { padding: 1.5rem; margin-bottom: 2rem; }
      .gallery-grid { grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); }
      .hero-links { flex-direction: column; gap: 1rem; }
    }
  </style>
</head>
<body>
  <!-- Header -->
  <header>
    <div class="container">
      <div class="header-content">
        <div class="logo">
          <h1>Dr. Manish Kumar</h1>
        </div>
        <div class="header-info">
          <div class="tagline">Assistant Professor, IIT (BHU) Varanasi</div>
          <a href="https://orcid.org/0000-0001-6053-3667" target="_blank" 
             class="orcid-badge" title="ORCID Profile">
            <span class="orcid-icon"></span>
            ORCID: 0000-0001-6053-3667
          </a>
        </div>
        <nav>
          <a href="#home" class="active">Home</a>
          <a href="#gallery">Gallery</a>
          <a href="#publications">Publications</a>
          <a href="#timeline">Career</a>
          <a href="#projects">Projects</a>
          <a href="#contact">Contact</a>
        </nav>
      </div>
    </div>
  </header>

  <!-- Hero -->
  <section id="home" class="hero">
    <div class="container">
      <h2>Bridging Theoretical Physics with Practical Energy Solutions</h2>
      <p>"I merge advanced theoretical physics with practical renewable energy applications to solve real-world power challenges."</p>
      <div class="hero-links">
        <a href="https://orcid.org/0000-0001-6053-3667" target="_blank" 
           class="orcid-badge" style="font-size: 1.1rem;">
          <span class="orcid-icon" style="width: 24px; height: 24px;"></span>
          ORCID: 0000-0001-6053-3667
        </a>
        <a href="https://www.linkedin.com/in/manish-kumar-87025815/" target="_blank">LinkedIn</a>
        <a href="mailto:kumarmanish8288@gmail.com">Email</a>
      </div>
    </div>
  </section>

  <!-- Gallery -->
  <section id="gallery">
    <div class="container">
      <h2>📸 Photo Gallery</h2>
      <p>Research visits, conferences, and project demonstrations.</p>
      <div class="gallery-grid">
        <figure class="gallery-item">
          <img src="assets/images/gallery/paris2022.jpg" alt="Paris Conference 2022" loading="lazy">
          <figcaption>Paris Conference, 2022</figcaption>
        </figure>
        <figure class="gallery-item">
          <img src="assets/images/gallery/prague2019.jpg" alt="Prague Terahertz Meeting" loading="lazy">
          <figcaption>Prague Terahertz Meeting, 2019</figcaption>
        </figure>
        <figure class="gallery-item">
          <img src="assets/images/gallery/meghalaya.jpg" alt="Meghalaya Field Visit" loading="lazy">
          <figcaption>Meghalaya Field Visit, 2015</figcaption>
        </figure>
        <figure class="gallery-item">
          <img src="assets/images/gallery/azamgarh.jpg" alt="Azamgarh Demo 2016" loading="lazy">
          <figcaption>Azamgarh Project Demo, 2016</figcaption>
        </figure>
      </div>
    </div>
  </section>

  <!-- Publications -->
  <section id="publications">
    <div class="container">
      <h2>📚 Peer-Reviewed Publications <a href="https://orcid.org/0000-0001-6053-3667" target="_blank" class="orcid-badge" style="font-size: 0.85rem; opacity: 0.8;">
        ORCID: 0000-0001-6053-3667
      </a></h2>
      <p>Searchable list of 14+ publications. Use the search box above table or filter by keywords like "THz", "plasma", "2019".</p>
      <table id="pubTable" class="display" style="width:100%"></table>
    </div>
  </section>

  <!-- Timeline (unchanged) -->
  <section id="timeline">
    <div class="container">
      <h2>🎓 Academic & Professional Journey</h2>
      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-date">Jul 2004 – Present</div>
          <div class="timeline-title">Assistant Professor, IIT (BHU) Varanasi</div>
          <p>13+ years teaching UG/PG, guided 1 PhD + 16 B.Tech projects, established CERD center</p>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">Nov 2001 – Jul 2004</div>
          <div class="timeline-title">Junior Telecom Officer, BSNL</div>
          <p>Managed BTS/BSC/MSC operations and CCN responsibilities</p>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">Jan 2008 – Dec 2010</div>
          <div class="timeline-title">Ph.D. Plasma Physics, IIT Delhi</div>
          <p>Thesis: Coherent Radiation Generation (CGPA: 8.00)</p>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">2000</div>
          <div class="timeline-title">M.Tech. Energy Studies, IIT Delhi</div>
          <p>CGPA: 8.5 | Project: Nonlinear Alfvén waves</p>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">1997</div>
          <div class="timeline-title">B.E. Electrical Engineering, MNNIT Allahabad</div>
          <p>69.22% | Project: Digital controller design</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects (unchanged) -->
  <section id="projects">
    <div class="container">
      <h2>🚀 Key Projects & Contributions</h2>
      <div class="projects-grid">
        <div class="project-card">
          <h3>1.5 MW Integrated Dairy & Smart Hybrid Energy Systems</h3>
          <p>Live demonstration in Azamgarh (2016), 5-acre pilot proposal for Meghalaya, prototype lab at IIT(BHU)</p>
        </div>
        <div class="project-card">
          <h3>Center for Energy Resources & Development (CERD)</h3>
          <p>Established under MHRD F.A.S.T. scheme at IIT(BHU)</p>
        </div>
        <div class="project-card">
          <h3>Book Publication</h3>
          <p><em>Coherent radiation generation by lasers and particle beams</em><br>ISBN: 978-3-659-84512-3, Scholar's Press, 2016</p>
        </div>
        <div class="project-card">
          <h3>Social Advocacy</h3>
          <p>Founder President, Denotified Tribes Welfare Association (DTWA). Filed WPIL 13206/2013 in Allahabad HC</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact (unchanged) -->
  <section id="contact">
    <div class="container">
      <h2>📞 Connect</h2>
      <div class="contact-grid">
        <div>
          <h3>Contact</h3>
          <p><strong>Office:</strong> kumarmanish8288@gmail.com</p>
          <p><strong>Personal:</strong> kumarmanish21@yahoo.com</p>
          <p><strong>Mobile:</strong> +91-8853951326, +91-7607101326</p>
        </div>
        <div>
          <h3>Personal</h3>
          <p><strong>DOB:</strong> 21-06-1974 | <strong>Nationality:</strong> Indian</p>
          <p><strong>Languages:</strong> English, Hindi</p>
          <p><strong>Hobbies:</strong> Astrophysics, Music, Chess, Cooking</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="container">
      <p>&copy; 2025 Dr. Manish Kumar | 
         <a href="https://orcid.org/0000-0001-6053-3667" target="_blank" class="orcid-badge">
           ORCID: 0000-0001-6053-3667
         </a> | 
         <a href="mailto:kumarmanish8288@gmail.com">Email</a> | 
         <a href="https://www.linkedin.com/in/manish-kumar-87025815/" target="_blank">LinkedIn</a> | 
         <a href="https://kumarmanish8288-sudo.github.io/kumarmanish2106">GitHub Pages</a>
      </p>
    </div>
  </footer>

  <!-- Publications JavaScript -->
  <script>
    $(document).ready(function() {
      // Load publications from BibTeX
      bibtexify("publications.bib", "pubTable", {
        template: "#default",
        datatable: {
          pageLength: 25,
          order: [[0, "desc"]],  
          pageLength: 50,
          dom: 'Bfrtip',
          buttons: ['copy', 'csv', 'excel', 'pdf', 'print']
        }
      });

      // Smooth scrolling for navigation
      $('nav a[href^="#"]').click(function(e) {
        e.preventDefault();
        $('html, body').animate({
          scrollTop: $($(this).attr('href')).offset().top - 80
        }, 800);
        $('nav a').removeClass('active');
        $(this).addClass('active');
      });
    });
  </script>
</body>
</html>
