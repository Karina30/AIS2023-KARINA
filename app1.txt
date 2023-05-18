import streamlit as st

# Set page config to wide layout
st.set_page_config(layout="wide")

# Set background image
background_image = "background_image"
page_bg_img = '''
<style>
body {
background-image: url("''' + background_image + '''");
background-size: cover;
}
</style>
'''
st.markdown(page_bg_img, unsafe_allow_html=True)

# Header and title
st.title('Welcome to Job Recommendation Portal')

# Skill selection
st.write('Please select one or more skills')

skills = [
    '.Net', 'AI', 'AWS', 'Azure', 'Big Data', 'Business Intelligence',
    'C#', 'C/C++', 'CI/CD', 'Cassandra', 'Data Analysis', 'Data Mining',
    'Data Science', 'Data Warehouse', 'Design Experience', 'Docker',
    'Elasticsearch', 'Excel', 'Git', 'Google Cloud Platform', 'HBase',
    'Hadoop', 'Hive', 'Informatica', 'Java', 'JavaScript', 'Kafka',
    'Linux', 'MATLAB', 'Machine Learning', 'Microsoft Office',
    'Microsoft Powerpoint', 'Microsoft SQL Server', 'MongoDB', 'MySQL',
    'Natural Language Processing', 'NoSQL', 'Oracle', 'Perl', 'Pig',
    'PostgreSQL', 'Power BI', 'Project Management', 'Python', 'R',
    'REST', 'Ruby', 'S3', 'SAS', 'SPSS', 'SQL', 'Scala', 'Scripting',
    'Shell Scripting', 'Software Development', 'Spark',
    'Statistical Analysis', 'TS/SCI Clearance', 'Tableau', 'TensorFlow'
]

selected_skills = st.multiselect('Skills', skills)

# Submit button
submitted = st.button('Submit')

# Job recommendation
if submitted:
    if len(selected_skills) < 1:
        st.write('Select at least one skill')
    else:
        st.write('Recommended jobs based on selected skills:')
        for skill in selected_skills:
            # Perform job recommendation based on selected skills
            # Replace the following line with your recommendation logic
            st.write('- Job related to ' + skill)
