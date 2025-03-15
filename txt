\documentclass[10pt, letterpaper]{article}

% Packages:
\usepackage[
    ignoreheadfoot, % set margins without considering header and footer
    top=2 cm, % seperation between body and page edge from the top
    bottom=2 cm, % seperation between body and page edge from the bottom
    left=2 cm, % seperation between body and page edge from the left
    right=2 cm, % seperation between body and page edge from the right
    footskip=1.0 cm, % seperation between body and footer
    % showframe % for debugging 
]{geometry} % for adjusting page geometry
\usepackage{titlesec} % for customizing section titles
\usepackage{tabularx} % for making tables with fixed width columns
\usepackage{array} % tabularx requires this
\usepackage[dvipsnames]{xcolor} % for coloring text
\definecolor{primaryColor}{RGB}{0, 0, 0} % define primary color
\usepackage{enumitem} % for customizing lists
\usepackage{fontawesome5} % for using icons
\usepackage{amsmath} % for math
\usepackage[
    pdftitle={Nguyen Ngoc Minh's CV},
    pdfauthor={Nguyen Ngoc Minh},
    pdfcreator={LaTeX with RenderCV},
    colorlinks=true,
    urlcolor=primaryColor
]{hyperref} % for links, metadata and bookmarks
\usepackage[pscoord]{eso-pic} % for floating text on the page
\usepackage{calc} % for calculating lengths
\usepackage{bookmark} % for bookmarks
\usepackage{lastpage} % for getting the total number of pages
\usepackage{changepage} % for one column entries (adjustwidth environment)
\usepackage{paracol} % for two and three column entries
\usepackage{ifthen} % for conditional statements
\usepackage{needspace} % for avoiding page brake right after the section title
\usepackage{iftex} % check if engine is pdflatex, xetex or luatex

% Ensure that generate pdf is machine readable/ATS parsable:
\ifPDFTeX
    \input{glyphtounicode}
    \pdfgentounicode=1
    \usepackage[T1]{fontenc}
    \usepackage[utf8]{inputenc}
    \usepackage{lmodern}
\fi

\usepackage{charter}

% Some settings:
\raggedright
\AtBeginEnvironment{adjustwidth}{\partopsep0pt} % remove space before adjustwidth environment
\pagestyle{empty} % no header or footer
\setcounter{secnumdepth}{0} % no section numbering
\setlength{\parindent}{0pt} % no indentation
\setlength{\topskip}{0pt} % no top skip
\setlength{\columnsep}{0.15cm} % set column seperation
\pagenumbering{gobble} % no page numbering

\titleformat{\section}{\needspace{4\baselineskip}\bfseries\large}{}{0pt}{}[\vspace{1pt}\titlerule]

\titlespacing{\section}{
    % left space:
    -1pt
}{
    % top space:
    0.3 cm
}{
    % bottom space:
    0.2 cm
} % section title spacing

\renewcommand\labelitemi{$\vcenter{\hbox{\small$\bullet$}}$} % custom bullet points
\newenvironment{highlights}{
    \begin{itemize}[
        topsep=0.10 cm,
        parsep=0.10 cm,
        partopsep=0pt,
        itemsep=0pt,
        leftmargin=0 cm + 10pt
    ]
}{
    \end{itemize}
} % new environment for highlights


\newenvironment{highlightsforbulletentries}{
    \begin{itemize}[
        topsep=0.10 cm,
        parsep=0.10 cm,
        partopsep=0pt,
        itemsep=0pt,
        leftmargin=10pt
    ]
}{
    \end{itemize}
} % new environment for highlights for bullet entries

\newenvironment{onecolentry}{
    \begin{adjustwidth}{
        0 cm + 0.00001 cm
    }{
        0 cm + 0.00001 cm
    }
}{
    \end{adjustwidth}
} % new environment for one column entries

\newenvironment{twocolentry}[2][]{
    \onecolentry
    \def\secondColumn{#2}
    \setcolumnwidth{\fill, 4.5 cm}
    \begin{paracol}{2}
}{
    \switchcolumn \raggedleft \secondColumn
    \end{paracol}
    \endonecolentry
} % new environment for two column entries

\newenvironment{threecolentry}[3][]{
    \onecolentry
    \def\thirdColumn{#3}
    \setcolumnwidth{, \fill, 4.5 cm}
    \begin{paracol}{3}
    {\raggedright #2} \switchcolumn
}{
    \switchcolumn \raggedleft \thirdColumn
    \end{paracol}
    \endonecolentry
} % new environment for three column entries

\newenvironment{header}{
    \setlength{\topsep}{0pt}\par\kern\topsep\centering\linespread{1.5}
}{
    \par\kern\topsep
} % new environment for the header

\newcommand{\placelastupdatedtext}{% \placetextbox{<horizontal pos>}{<vertical pos>}{<stuff>}
  \AddToShipoutPictureFG*{% Add <stuff> to current page foreground
    \put(
        \LenToUnit{\paperwidth-2 cm-0 cm+0.05cm},
        \LenToUnit{\paperheight-1.0 cm}
    ){\vtop{{\null}\makebox[0pt][c]{
        \small\color{gray}\textit{Last updated in March 2025}\hspace{\widthof{Last updated in March 2025}}
    }}}%
  }%
}%

% save the original href command in a new command:
\let\hrefWithoutArrow\href

\begin{document}
    \newcommand{\AND}{\unskip
        \cleaders\copy\ANDbox\hskip\wd\ANDbox
        \ignorespaces
    }
    \newsavebox\ANDbox
    \sbox\ANDbox{$|$}

    \begin{header}
        \fontsize{25 pt}{25 pt}\selectfont NGUYEN NGOC MINH

        \vspace{5 pt}

        \normalsize
        \mbox{Ho Chi Minh City, Vietnam}%
        \kern 5.0 pt%
        \AND%
        \kern 5.0 pt%
        \mbox{\hrefWithoutArrow{mailto:ngocminhit2000@gmail.com}{ngocminhit2000@gmail.com}}%
        \kern 5.0 pt%
        \AND%
        \kern 5.0 pt%
        \mbox{\hrefWithoutArrow{tel:+84-886-045-188}{(+84) 886 045 188}}%
        \kern 5.0 pt%
        \AND%
        \kern 5.0 pt%
        \mbox{\hrefWithoutArrow{https://github.com/minhnndev}{github.com/minhnndev}}%
        \kern 5.0 pt%
        \AND%
        \kern 5.0 pt%
        \mbox{\hrefWithoutArrow{https://www.linkedin.com/in/minhnndev}{linkedin.com/in/minhnndev}}%
    \end{header}

    \vspace{5 pt - 0.3 cm}

    \section{Summary}
        
    \begin{onecolentry}
        I'm a Front-end Engineer with 3 years of experience who specializes in building high-quality mobile applications using React Native technology and with a deep understanding of Javascript frameworks and have successfully created complex applications, include Super App architecture. I have experience working with large systems such as Micro-services and am skilled in integrating third-party APIs, software development and management using the Agile (Scrum) methodology. I emphasize the importance of code testing and reviews to maintain a high-quality codebase. Additionally, I have strong problem-solving skills and a passion for staying current with the latest technologies and best practices.
    \end{onecolentry}

    \vspace{0.2 cm}

    \begin{onecolentry}
        I am a committed team player with expertise in collaborating with cross-functional teams to deliver exceptional results. I am confident in my ability to contribute to any project or organization.
    \end{onecolentry}

    \section{Education}
        
    \begin{twocolentry}{
        2018 – 2022
    }
        \textbf{Thu Dau Mot University}, Engineering's Degree in Software Engineering\end{twocolentry}

    \vspace{0.10 cm}
    \begin{onecolentry}
        \begin{highlights}
            \item GPA: 3.62/4.0
            \item Graduated June 2022
        \end{highlights}
    \end{onecolentry}

    \section{Experience}

    \begin{twocolentry}{
        May 2023 – Present
    }
        \textbf{Front-end Engineer}, NEWAI JOINT STOCK COMPANY -- Start-up AI - Application AI Chat GPT\end{twocolentry}

    \vspace{0.10 cm}
    \begin{onecolentry}
        \begin{highlights}
            \item Mainly responsible for application development at the company (Team size: 1)
            \item Possessing experience in core modules, chat, high-performance caching, and application performance optimization, as well as proficiency in Google Cloud clean code practices and release app
            \item Contributing to the definition and creation of features, design, and user experience
            \item Furthermore, contributing to the construction of system architecture and actively participating in DevOps tasks, such as setting up CDNs on Google Cloud, S3 on AWS, and Firebase
            \item Technology: React Native, RestfulAPI, Redux, Firebase, Github CI/CD, AppCenter, Fastlane
            \item App Store: \href{https://apps.apple.com/us/app/kamimind/id6466782475}{https://apps.apple.com/us/app/kamimind/id6466782475}
            \item Google Play: \href{https://play.google.com/store/apps/details?id=com.kamimind}{https://play.google.com/store/apps/details?id=com.kamimind}
        \end{highlights}
    \end{onecolentry}

    \vspace{0.2 cm}

    \begin{twocolentry}{
        May 2024 – Present
    }
        \textbf{Full-stack Developer}, NEWAI JOINT STOCK COMPANY\end{twocolentry}

    \vspace{0.10 cm}
    \begin{onecolentry}
        \begin{highlights}
            \item Primarily responsible for product development, bug fixing, and product maintenance on the website and mobile
            \item Website: \href{https://kamimind.ai/}{https://kamimind.ai/}
        \end{highlights}
    \end{onecolentry}

    \vspace{0.2 cm}

    \begin{twocolentry}{
        Dec 2021 – Feb 2023
    }
        \textbf{Mobile Application Developer}, M\_SERVICE JSC. (MoMo E-Wallet) -- Super application the leading E-Wallet with more than 30 million users in Vietnam\end{twocolentry}

    \vspace{0.10 cm}
    \begin{onecolentry}
        \begin{highlights}
            \item Team: MoMo E-Wallet Application – Financial Service – Team Insurance
            \item Team size: A team of 7 back-end developers, 3 mobile app developers, and 2 QC team members
            \item Optimize the Insurance contract management: Successfully reduced screen the initial load time from 2.4 seconds to 0.8 seconds (~67\%), and subsequent load times from 0.8 seconds down to only 0.2 - 0.3 seconds (~70\%), resulting in improved user experience
            \item Technology: iOS, React Native, RestfulAPI, Redux, Zustand
        \end{highlights}
    \end{onecolentry}

    \section{Projects}

    \begin{twocolentry}{
        Feb 2023 – Present
    }
        \textbf{MEETDY - PRODUCTIVITY FOR WORK}, Personal product\end{twocolentry}

    \vspace{0.10 cm}
    \begin{onecolentry}
        \begin{highlights}
            \item Meetdy application Chat for work - The application was created with the purpose of providing chat tools for work in businesses and expand other tools such as attendance, task management, calendar, email, etc.
            \item Technology (micro-service with):
            \begin{itemize}
                \item Frontend: React Native (Mobile), React, NextJS, RestfulAPI, Redux, Firebase
                \item Backend: NodeJs, Go, SocketIO, WebRTC, Kubernetes (K3s), Argo
                \item Database \& Cloud: MongoDB, AWS S3, Google Cloud Message
                \item Deploy: Website is being deployed by Vercel, Backend and Redis deployed by Render, and MongoDB Atlas \& Self-host
            \end{itemize}
            \item Website: \href{https://meetdy.com}{https://meetdy.com}
        \end{highlights}
    \end{onecolentry}

    \vspace{0.2 cm}

    \begin{twocolentry}{
        Aug 2022 – Oct 2022
    }
        \textbf{HANOI REPAIR APPLICATION}, Freelancer\end{twocolentry}

    \vspace{0.10 cm}
    \begin{onecolentry}
        \begin{highlights}
            \item The application provides repair and installation services for home appliances, can order the service provided on the app
            \item As the lead application developer, collaborated closely with backend developers and contributed to the development process
            \item Developed applications based on customer requirements and provided valuable suggestions for enhancing product quality
            \item Technology: React Native, RestfulAPI, Redux, Firebase, MongoBD, Docker, CI/CD
            \item App Store: \href{https://apps.apple.com/vn/app/hanoirepairapp}{https://apps.apple.com/vn/app/hanoirepairapp}
            \item Google Play: \href{https://play.google.com/store/apps/details?id=com.hanoirepairapp}{https://play.google.com/store/apps/details?id=com.hanoirepairapp}
        \end{highlights}
    \end{onecolentry}

    \section{Skills}

    \begin{onecolentry}
        \textbf{Technologies:} React Native, ReactJS, NextJS, NodeJS (Express), Redux (Saga, Thunk), RestfulAPI, Firebase, TypeScript, GraphQL
    \end{onecolentry}

    \vspace{0.2 cm}

    \begin{onecolentry}
        \textbf{Other:} Git, Google Cloud Platform, Docker, Jenkins, CI/CD, Redis, Unit Test(Jest)
    \end{onecolentry}

    \section{Honor \& Awards}

    \begin{onecolentry}
        \begin{highlightsforbulletentries}
            \item ACM/ICPC 27th Asian Hanoi 2018
            \item Consolation Prize Olympic Programing Specializing Informatics In University 2019
            \item Second Prize in Scientific research at the university level
            \item Certificate Google Cloud Fundamentals: Core Infrastructure: Certificate
            \item Certificate Agile with Atlassian Jira: Certificate
        \end{highlightsforbulletentries}
    \end{onecolentry}
\end{document}
