# bestkaunas.org

### Running locally
- Install Docker and Docker-compose (or Docker Desktop)
- Download git repository
- Extract exported website files into `files`
- Run command `docker-compose up`
- Access database through http://localhost:8050/
- Import exported database
- Run SQL script to change URL from `bestkaunas.org` to `localhost`:
  ```sql
  UPDATE best_db.wp_options t
  SET t.option_value = 'http://localhost'
  WHERE t.option_name IN ('siteurl', 'home');
  ```
- Access website at http://localhost/

### Deploying to production
- Set database connection details in `files/wp-config.php`
- Upload files trough FTP
- If importing database to production, don't forget to change back URLs:
  ```sql
  UPDATE best_db.wp_options t
  SET t.option_value = 'https://bestkaunas.org'
  WHERE t.option_name IN ('siteurl', 'home');
  ```
