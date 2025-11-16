# Cloud Dashboard

An interactive cloud infrastructure visualization dashboard that reveals which companies depend on which cloud providers and explores AWS regions worldwide. When AWS goes down, Netflix, Reddit, and Slack go with it—this dashboard shows you exactly who controls the internet.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Next.js](https://img.shields.io/badge/Next.js-15.2-black)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)](https://www.typescriptlang.org/)

## 📋 Table of Contents

- [Cloud Dashboard](#cloud-dashboard)
  - [📋 Table of Contents](#-table-of-contents)
  - [About The Project](#about-the-project)
    - [Key Insights](#key-insights)
    - [What Makes It Unique](#what-makes-it-unique)
    - [Built With](#built-with)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [Usage](#usage)
    - [Cloud Dependency Explorer](#cloud-dependency-explorer)
    - [AWS Regions Explorer](#aws-regions-explorer)
    - [Cloud Provider Detection API](#cloud-provider-detection-api)
    - [Key Features](#key-features)
  - [Screenshots](#screenshots)
    - [Cloud Dependency Dashboard](#cloud-dependency-dashboard)
    - [AWS Regions Explorer](#aws-regions-explorer-1)
    - [Cloud Provider Detection](#cloud-provider-detection)
  - [Roadmap](#roadmap)
  - [Contributing](#contributing)
    - [How to Contribute](#how-to-contribute)
    - [Areas for Contribution](#areas-for-contribution)
  - [License](#license)
  - [Contact](#contact)
  - [Technical Details](#technical-details)
    - [Project Structure](#project-structure)
    - [Cloud Detection Algorithm](#cloud-detection-algorithm)
    - [Data Sources](#data-sources)
  - [Acknowledgments](#acknowledgments)
  - [Disclaimer](#disclaimer)

## About The Project

Cloud Dashboard is an interactive visualization tool that answers a critical question: **Who controls the internet?** 

The project reveals the hidden dependencies between major companies and cloud providers (AWS, Azure, GCP, Oracle, Alibaba). It demonstrates how a single cloud provider outage can bring down hundreds of major services simultaneously—as seen when AWS outages affect Netflix, Reddit, Slack, and countless other platforms.

### Key Insights
- **Market Concentration**: Visualize how the "Big 3" (AWS, Azure, GCP) control the majority of internet infrastructure
- **Real-time Detection**: Add any company URL and automatically detect which cloud provider they use
- **Global Infrastructure**: Explore AWS regions worldwide on an interactive 3D globe
- **Dependency Mapping**: Understand the true scale of cloud provider concentration

### What Makes It Unique
- **Automatic Cloud Detection**: Uses HTTP headers and content analysis to identify cloud providers
- **Interactive 3D Globe**: D3.js-powered rotating Earth visualization of AWS datacenter locations
- **Real-time Company Addition**: Dynamically add companies and see market share updates instantly
- **Beautiful UI**: Modern, dark-themed interface with smooth animations and responsive design

### Built With

- **[Next.js 15](https://nextjs.org/)** - React framework with App Router
- **[React 19](https://reactjs.org/)** - UI library
- **[TypeScript](https://www.typescriptlang.org/)** - Type safety
- **[Tailwind CSS 4](https://tailwindcss.com/)** - Utility-first styling
- **[D3.js](https://d3js.org/)** - 3D globe visualization and geographic projections
- **[Recharts](https://recharts.org/)** - Interactive charts and data visualization
- **[Radix UI](https://www.radix-ui.com/)** - Accessible component primitives
- **[Vercel Analytics](https://vercel.com/analytics)** - Web analytics

## Getting Started

### Prerequisites

- **Node.js** v18 or higher
- **npm**, **yarn**, or **pnpm** package manager
- **Git** for cloning the repository

### Installation

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/CloudDashborad.git
   cd CloudDashborad
   ```

2. Install dependencies
   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   ```

3. Run the development server
   ```bash
   npm run dev
   # or
   yarn dev
   # or
   pnpm dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

The app will start with a pre-loaded dataset of major companies and their cloud providers. No environment variables or API keys are required for basic functionality.

## Usage

### Cloud Dependency Explorer

The main dashboard shows companies organized by cloud provider:

1. **Search Companies**: Type a company name or domain (e.g., "Netflix" or "stripe.com")
2. **Filter by Provider**: Click provider pills (AWS, Azure, GCP, etc.) to filter companies
3. **Add New Companies**: Enter a URL or domain and press Enter to auto-detect the cloud provider
4. **View Market Share**: Interactive pie chart shows provider distribution
5. **Hover Interactions**: Hover over chart segments to highlight companies

### AWS Regions Explorer

Explore AWS datacenter locations worldwide:

1. Click **"Cloud Regions"** button in the top-right
2. **Search Regions**: Use the search bar to find regions by name, code, or AWS region ID
3. **Select Regions**: Click a region to zoom on the globe, or Cmd/Ctrl+click for multi-select
4. **View Details**: Click the info icon to see detailed region information
5. **Resize Sidebar**: Drag the right edge to adjust sidebar width

### Cloud Provider Detection API

The app includes an API endpoint that automatically detects cloud providers:

```typescript
// POST /api/detect-cloud
const response = await fetch('/api/detect-cloud', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ url: 'https://example.com' })
})

const result = await response.json()
// { provider: 'AWS', confidence: 'high', signals: [...] }
```

### Key Features

- **Interactive Visualizations**: Pie charts, treemaps, and 3D globe with smooth animations
- **Real-time Cloud Detection**: Automatically identify cloud providers from HTTP headers
- **Company Database**: Pre-loaded with 100+ major companies (S&P 500, tech giants)
- **Dynamic Company Addition**: Add any company URL and see instant market share updates
- **AWS Region Mapping**: Complete dataset of AWS regions, availability zones, and local zones
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Dark Theme**: Beautiful emerald-themed UI optimized for data visualization

## Screenshots

### Cloud Dependency Dashboard
The main view showing companies organized by cloud provider with interactive charts and market share statistics.

### AWS Regions Explorer
Interactive 3D globe visualization showing AWS datacenter locations worldwide with searchable region list and detailed information panels.

### Cloud Provider Detection
Real-time detection of cloud providers by analyzing HTTP headers and content from any URL.

## Roadmap

Planned features and improvements:

- [ ] **Multi-Cloud Support**: Add Azure, GCP, Oracle, and Alibaba region explorers
- [ ] **Historical Data**: Track cloud provider migrations over time
- [ ] **Outage Impact Analysis**: Show which companies are affected during cloud outages
- [ ] **Export Functionality**: Export company lists and visualizations as CSV/PNG
- [ ] **Company Details Panel**: Show more information about each company (industry, revenue, etc.)
- [ ] **Region Comparison**: Compare latency, pricing, and features across regions
- [ ] **API Rate Limiting**: Add rate limiting to cloud detection API
- [ ] **Caching**: Implement caching for cloud detection results
- [ ] **Bulk Import**: Import multiple companies from CSV or JSON
- [ ] **Real-time Updates**: WebSocket support for live market share updates

See the [open issues](https://github.com/yourusername/CloudDashborad/issues) for a full list of proposed features and known issues.

## Contributing

Contributions are welcome! This project aims to raise awareness about cloud concentration and infrastructure dependencies.

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Make your changes** following the existing code style
4. **Test your changes** (`npm run build` and `npm run lint`)
5. **Commit your changes** (`git commit -m 'Add some AmazingFeature'`)
6. **Push to the branch** (`git push origin feature/AmazingFeature`)
7. **Open a Pull Request**

### Areas for Contribution

- **Data Accuracy**: Help verify and update company cloud provider information
- **New Features**: Implement items from the roadmap
- **UI/UX Improvements**: Enhance visualizations and user experience
- **Performance**: Optimize rendering and API calls
- **Documentation**: Improve code comments and user guides
- **Testing**: Add unit and integration tests

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

Project Link: [https://github.com/yourusername/CloudDashborad](https://github.com/yourusername/CloudDashborad)

## Technical Details

### Project Structure

```
CloudDashborad/
├── app/
│   ├── api/detect-cloud/    # Cloud provider detection API
│   ├── layout.tsx            # Root layout with metadata
│   └── page.tsx             # Main page router
├── components/
│   ├── aws-regions-explorer.tsx    # AWS regions visualization
│   ├── cloud-dependency-explorer.tsx  # Main dashboard
│   ├── rotating-earth.tsx          # 3D globe component
│   └── ui/                          # Reusable UI components
├── lib/
│   ├── company-data.ts      # Company dataset
│   └── utils.ts             # Utility functions
└── public/
    ├── aws-regions.json      # AWS region data
    └── *.json                # Additional region metadata
```

### Cloud Detection Algorithm

The cloud detection API analyzes:
- **HTTP Headers**: X-Amz-*, X-Azure-*, X-Goog-* headers
- **Server Headers**: Server identification strings
- **Via Headers**: CDN and proxy information
- **Content Analysis**: Domain mentions in HTML content
- **Confidence Levels**: High, medium, or low based on signal strength

### Data Sources

- **Company Data**: Curated dataset based on public information and reports
- **AWS Regions**: Official AWS region identifiers and metadata
- **Region Mapping**: Comprehensive mapping of region codes to identifiers

## Acknowledgments

- **D3.js** - Powerful data visualization library for the globe
- **Recharts** - Beautiful chart components
- **Radix UI** - Accessible component primitives
- **Next.js Team** - Amazing React framework
- **AWS** - For comprehensive region documentation
- **Clearbit Logo API** - Company logo service
- All contributors and users who help improve this project

## Disclaimer

This project is for educational and informational purposes. Cloud provider assignments are based on public information and may not reflect current or complete infrastructure setups. Companies often use multiple cloud providers, and the data represents primary or publicly disclosed providers.
