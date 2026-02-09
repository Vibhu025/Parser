# 🛡️ Security Tools Suite - Network & API Analysis Platform

<div align="center">

![Version](https://img.shields.io/badge/version-3.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Security](https://img.shields.io/badge/security-XSS%20Protected-brightgreen)
![Offline](https://img.shields.io/badge/offline-100%25-success)

A professional, high-performance, **single-file HTML application** combining two powerful security analysis tools: **Nmap Report Analyzer** and **Postman Collection Analyzer**. Built specifically for security researchers, penetration testers, bug bounty hunters, and developers who need comprehensive network and API reconnaissance capabilities.

[Features](#-key-features) • [Tools](#-included-tools) • [Usage](#-quick-start) • [Security](#-security-specifications) • [Contributing](#-contributing)

</div>

---

## 🎯 Why Use This Suite?

Modern security assessments require analyzing both **network infrastructure** and **API surfaces**. This unified platform provides:

- **Network Reconnaissance**: Parse Nmap scan results to identify open ports, services, and vulnerabilities
- **API Surface Mapping**: Analyze Postman collections to understand API endpoints, methods, and attack vectors
- **Unified Workflow**: Switch seamlessly between network and API analysis in a single interface
- **Offline Security**: Zero external dependencies - perfect for air-gapped or sensitive environments
- **Professional Reporting**: Export clean, formatted reports suitable for penetration testing deliverables

---

## 🚀 Key Features

### 🔐 **Enterprise-Grade Security**
- **100% Offline**: Operates entirely within your browser using HTML5 File API
- **Zero Server Communication**: No data ever leaves your machine
- **XSS Protected**: Comprehensive input sanitization and output encoding
- **No Dependencies**: No CDN calls, external libraries, or tracking
- **Air-Gap Compatible**: Works in isolated/restricted network environments
- **Session-Only Storage**: All data cleared on page refresh

### 🎨 **Modern, Responsive UI**
- **Elegant Sidebar Navigation**: Quick switching between tools
- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Dark-Themed Sidebar**: Professional aesthetic with gradient accents
- **Collapsible Sections**: Auto-collapse upload areas after processing
- **Print-Optimized**: Clean printouts for documentation and reports

### ⚡ **High Performance**
- **Single-File Application**: No build process or installation required
- **Efficient Parsing**: Handles large datasets (1000+ endpoints, 1000+ ports)
- **Debounced Search**: Smooth filtering even with massive datasets
- **Progressive Rendering**: Responsive UI during heavy operations

---

## 🛠️ Included Tools

### 1️⃣ **Nmap Report Analyzer** 🔒

A comprehensive network scanning analysis tool that transforms Nmap output into actionable intelligence.

#### **Supported Formats**
- ✅ **XML Output** (`.xml`) - Full structured Nmap data
- ✅ **Normal Output** (`.nmap`) - Standard text format  
- ✅ **Text Files** - Plain text Nmap output

#### **Core Features**
- 📊 **Real-Time Statistics Dashboard**
  - Total hosts scanned
  - Open/Closed/Filtered port counts
  - Unique services discovered
  - Total ports analyzed

- 🎯 **Critical Service Detection**
  - Automatically flags high-risk services (SSH, RDP, FTP, Telnet, SMB, databases)
  - Animated critical badges for immediate visibility
  - Exportable critical findings list

- 🔍 **Advanced Filtering**
  - Filter by IP address
  - Filter by port state (open/closed/filtered)
  - Real-time search across all fields
  - Multi-criteria filtering

- 📤 **Export Capabilities**
  - CSV export with full data
  - Print-optimized reports
  - Filtered results export

#### **Use Cases**
- External/Internal network reconnaissance
- Vulnerability assessment preparation
- Service enumeration for penetration testing
- Network inventory documentation
- Compliance auditing (PCI-DSS, HIPAA)

---

### 2️⃣ **Postman Collection Analyzer** ⚡

A sophisticated API surface analysis tool for security researchers and developers.

#### **Smart URL Normalization**
- **Preserves API Versioning**: `v1`, `v2`, `v3` segments remain intact
- **Dynamic ID Tokenization**:
  - UUIDs → `{uuid}` (`550e8400-e29b-41d4-a716-446655440000` → `{uuid}`)
  - Numeric IDs → `{id}` (`/users/123` → `/users/{id}`)
  - Query parameters → `{id}` (`?userId=456` → `?userId={id}`)
- **No URL Encoding**: Displays `{id}` not `%7Bid%7D`

#### **Deep Variable Resolution**
- Recursively resolves Postman `{{variable}}` syntax (up to 15 iterations)
- Handles complex nested variables: `{{protocol}}://{{baseUrl}}:{{port}}`
- Supports multiple environment files simultaneously
- Auto-fixes malformed JSON environment files

#### **Intelligent Deduplication**
- Removes duplicates based on `METHOD + NORMALIZED_URL`
- Tracks duplicate count in dashboard
- Handles cross-collection duplicates
- Preserves original URLs for reference

#### **Professional Reporting**
- 🖥️ **Terminal-Style Output**: Monospaced, clean formatting
- **Two Display Modes**:
  - **Grouped**: `[GET,POST,PUT] /api/users/{id}`
  - **One Per Line**: Detailed method-by-method listing
- **Host-Based Grouping**: Automatic domain extraction and grouping
- **Export to TXT**: Formatted reports with metadata

#### **Advanced Filtering**
- Filter by HTTP method (GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD)
- Real-time search across paths, methods, names
- Multi-sort options (path, method, name - ascending/descending)
- Debounced search for performance

#### **Dashboard Metrics**
- **Unique Endpoints**: Distinct API routes after normalization
- **Total Methods**: Count of different HTTP methods
- **Total Requests**: Aggregate requests from all collections
- **Duplicates Removed**: Filtered duplicate endpoints

#### **Use Cases**
- API security testing preparation
- Bug bounty reconnaissance
- API documentation generation
- Endpoint inventory for GraphQL migration
- OAuth scope mapping
- Rate limiting analysis

---

## 🚀 Quick Start

### Using Nmap Analyzer

1. **Navigate**: Open the [Link](https://vibhu025.github.io/parser/) in any modern web browser (Chrome, Firefox, Edge, Safari)
2. **Upload Files**: 
   - Click the upload zone or drag-and-drop files
   - Supports `.xml`, `.nmap`, or text output files
   - Multiple files supported
3. **Analyze**: Click "Parse Files" 
4. **Filter & Search**:
   - Use IP filter dropdown
   - Select port state (open/closed/filtered)
   - Search by IP, service, port, or details
5. **Export**: Click "Export CSV" for spreadsheet analysis

### Using Postman Analyzer

1. **Navigate**: Open the [Link](https://vibhu025.github.io/parser/) in any modern web browser (Chrome, Firefox, Edge, Safari)
2. **Upload Collections**:
   - **Collection Files**: Select one or more Postman collection JSON files
   - **Environment Files** (optional): Select environment variable files
3. **Parse**: Click "Parse Collections"
4. **Filter & Analyze**:
   - Toggle HTTP methods on/off
   - Use search box for real-time filtering
   - Change sort order
   - Toggle layout mode (grouped vs. one-per-line)
5. **Review**: Expand "All Endpoints" accordion to see original URLs
6. **Export**: Click "Export to TXT" for formatted report

---

## 📊 Feature Comparison

| Feature | Nmap Analyzer | Postman Analyzer |
|---------|---------------|------------------|
| **Input Format** | XML, .nmap, text | JSON (v2.0/v2.1) |
| **Multi-File Support** | ✅ | ✅ |
| **Real-Time Filtering** | ✅ | ✅ |
| **Search Capability** | ✅ | ✅ |
| **Export Options** | CSV | TXT |
| **Auto-Collapse Upload** | ✅ | ✅ |
| **Print Support** | ✅ | ✅ |
| **Statistics Dashboard** | ✅ | ✅ |
| **Offline Operation** | ✅ | ✅ |
| **Mobile Responsive** | ✅ | ✅ |

---

## 🔒 Security Specifications

### Privacy & Data Handling
- ✅ **No LocalStorage**: No persistent browser storage
- ✅ **No Cookies**: Zero cookie usage
- ✅ **No Analytics**: No tracking or telemetry
- ✅ **No External Calls**: No CDN, API, or network requests
- ✅ **Session-Only**: All data cleared on page refresh
- ✅ **Client-Side Processing**: 100% browser-based computation

### XSS Protection
- ✅ **Input Sanitization**: All file inputs validated
- ✅ **Output Encoding**: HTML escaping for all displayed content
- ✅ **CSP Ready**: Compatible with Content Security Policy
- ✅ **No eval()**: No dynamic code execution
- ✅ **Safe URL Parsing**: Protected against malicious URLs

### Compliance
- ✅ **GDPR Compliant**: No personal data collection
- ✅ **Air-Gap Compatible**: Works in isolated environments
- ✅ **SOC 2 Compatible**: Suitable for audited environments
- ✅ **HIPAA Friendly**: No PHI exposure risk

---

## 🐛 Known Limitations

### Nmap Analyzer
- **Large Files**: Scans with 5000+ ports may cause browser slowdown
- **Custom Scripts**: Nmap NSE script output not parsed
- **OS Detection**: Operating system detection data not displayed
- **Traceroute**: Traceroute information not included

### Postman Analyzer
- **Collection Size**: 1000+ endpoints may slow filtering
- **Postman Versions**: Optimized for v2.0/v2.1 format
- **GraphQL**: GraphQL queries not normalized
- **Authentication**: Auth headers not analyzed
- **Export Formats**: Only TXT export (CSV/JSON coming soon)

### General
- **Browser Memory**: Very large datasets may hit browser memory limits
- **File Size**: Files larger than 50MB may not load on mobile devices
- **Print Layout**: Complex tables may break across pages

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Report Issues
- **Bug Reports**: Use the issue template with reproduction steps
- **Feature Requests**: Describe the use case and expected behavior
- **Documentation**: Help improve clarity or add examples

### Submit Code
1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Development Guidelines
- Maintain single-file architecture
- Preserve offline functionality
- Add comments for complex logic
- Ensure XSS protection for new features
- Test on all major browsers
- Update documentation

### Code Style
```javascript
// Use descriptive variable names
const parsedEndpoints = [];

// Add JSDoc comments for functions
/**
 * Normalizes a URL by replacing dynamic segments
 * @param {string} url - The URL to normalize
 * @returns {string} Normalized URL with placeholders
 */
function normalizeUrl(url) { ... }

// Use template literals
const message = `Parsed ${count} endpoints`;

// Prefer const/let over var
const data = [];
let currentFilter = 'all';
```

---

## 📞 Support

- **Issues**: Open an issue on GitHub
- **Discussions**: Use GitHub Discussions for questions
- **Security**: Report security issues privately via email

---

## 🌟 Star History

If this tool helped you, please consider giving it a star ⭐ to help others discover it!

---

<div align="center">

Made with ❤️ for the security and developer community

[Report Bug](../../issues) • [Request Feature](../../issues) • [Documentation](../../wiki)

</div>
