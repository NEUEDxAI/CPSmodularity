# CPS Skills Extraction Portal

### **Project Overview**

The **CPS Skills Extraction Portal** is a sophisticated web-based application designed to automate the extraction and management of skills data from academic course syllabi. By leveraging advanced AI technologies and integrating with skill extraction tool called Lightcast, the portal provides us with an efficient tool to process, analyze, and store critical course information and associated skills. The key objectives of the project include:

1. **Automation of Data Extraction:**
   - Eliminate the need for manual extraction of skills and course details from syllabi.
   - Reduce the time and effort required to process large volumes of course documents.

2. **Enhanced Data Accuracy and Consistency:**
   - Utilize advanced AI tools to ensure high precision in extracting relevant information.
   - Maintain consistency in data extraction across different documents and formats.

3. **Scalability and Efficiency:**
   - Support both single and batch uploads, allowing for the processing of individual files or bulk datasets seamlessly.
   - Handle diverse file formats, including PDF and DOCX, to accommodate various syllabus templates.

4. **Comprehensive Data Management:**
   - Store extracted data in a structured and centralized database for easy retrieval and analysis.
   - Provide intuitive data visualization and export functionalities to support reporting and strategic planning.

Application Link: https://cps-modularity.streamlit.app/

---

### **Key Features**

1. **Syllabi Skill Extraction**
   - **File Upload Options:**
     - **Single Upload:** Allows users to upload individual course syllabi in PDF or DOCX formats.
     - **Batch Upload:** Supports uploading multiple syllabi packaged in a ZIP file for streamlined processing.
   - **Document Processing:**
     - **Text Extraction:** Allows users to extract text content from PDF and DOCX files respectively.
     - **Course Detail Extraction:** Employs OpenAI’s GPT-4 model to parse syllabus content and extract structured course details such as course code, title, instructor information, term, length, credit hours, format, description, learning outcomes, and schedule.
   - **Skill Extraction:**
     - Integrates with Lightcast’s API to identify and extract relevant skills from the course content.
     - Features a confidence threshold slider to adjust the precision of skill extraction results.
   - **Database Integration:**
     - Option to upload extracted data to a Supabase database, facilitating persistent storage and future retrieval.

2. **Lightcast Skill Extractor**
   - Dedicated interface for extracting skills directly using Lightcast’s API from any kind of document.
   - Supports multiple file types and provides real-time detailed list of all the skills that have been extracted from the document.

3. **Skills Viewer**
   - **Data Visualization:**
     - Displays extracted skills data in an organized and user-friendly format.
     - Allows users to filter data based on selectable date ranges to focus on specific timeframes.
   - **Data Export:**
     - Provides functionality to download filtered data as CSV files for offline analysis and reporting.
   - **Database Interaction:**
     - Fetches and displays data from Supabase tables, ensuring seamless access to stored information.

---

### **Technologies Used**

- **Frontend Framework:** [Streamlit](https://streamlit.io/)
  - Facilitates the creation of interactive and responsive web interfaces using Python.
  
- **Backend Services:**
  - **OpenAI GPT-4:** Powers the extraction of structured course details from unstructured syllabus text.
  - **Lightcast API:** Handles the extraction of relevant skills from course content.
  - **Supabase:** Serves as the cloud-based database for storing extracted course and skills data.

---

### **Project Workflow**

1. **Authentication:**
   - Users provide Lightcast credentials (client ID and client secret) to authenticate and obtain access tokens for API interactions.

2. **File Upload and Processing:**
   - Users upload course syllabi through the Streamlit interface, selecting either single or batch upload options.
   - The application reads and extracts text from the uploaded documents using appropriate libraries based on file type.
   
3. **Data Extraction:**
   - Extracted text is processed by OpenAI’s GPT-4 model to obtain structured course details in JSON format.
   - The structured course information is then sent to Lightcast’s API to extract associated skills, adhering to the user-defined confidence threshold.

4. **Data Display and Storage:**
   - Extracted course details and skills are presented to the user in an organized manner within the application.
   - Users can choose to upload the extracted data to a Supabase database for persistent storage, enabling future access and analysis.

5. **Data Management:**
   - In the **Skills Viewer** tab, users can query and view stored skills data based on specified date ranges.
   - The application provides options to download the filtered data as CSV files for offline use.

---

## Installation

To set up the project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Draconian10/CPS_Modularity.git
   ```

2. **Install the required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
   
3. **Set up environment variables**:
   Create a `.env` file in the root directory of the project and add the following environment variables:
   ```
   SUPABASE_URL=your_supabase_url
   SUPABASE_KEY=your_supabase_key
   OPENAI_API_KEY=your-openai_api_key
   CLIENT_ID=your_lightcast_client_id
   CLIENT_SECRET=your_lightcast_client_secret
   ```
   
4. **Run the application**:
   ```bash
   streamlit run Lightcast_UG.py
   ```
