```mermaid
erDiagram
    actors {
        actor_id int PK
        name string
        gender string
    }

    casts {
        movie_id int
        character string
        credit_id string
        actor_id int FK
        order int
    }

    workers {
        worker_id int PK
        name sting
        gender string
    }

    crews {
        movie_id int
        credit_id sting
        department string
        worker_id int FK
        job string 
    }

    genres_type {
        genre_id int PK
        name sting
    }

    genres {
        movie_id int
        genre_id int FK
    }

    keyword_type {
        keywork_id int PK
        name sting
    }

    keywords {
        movie_id int
        keyword_id int FK
    }

    production_company_type {
        production_company_id int PK
        name sting
    }

    production_companies {
        movie_id int
        production_company_id int FK
    }

    production_country_type {
        iso_3166_1 string PK
        name sting
    }

    production_countries {
        movie_id int
        iso_3166_1 string FK
    }
    
    spoken_language_type {
        iso_639_1 string PK
        name sting
    }

    spoken_languages {
        movie_id int
        iso_639_1 string FK
    }

    movies {
        budget int
        homepage string
        movie_id int PK
        original_language string
        original_title string
        overview string
        popularity double
        release_date date
        revenue int
        runtime double
        status string
        tagline string
        title string
        vote_average double
        vote_count int
    }

    movies ||--|{ casts : movie_id
    movies ||--|{ crews : movie_id
    movies ||--|{ genres : movie_id
    movies ||--|{ keywords : movie_id
    movies ||--|{ production_companies : movie_id
    movies ||--|{ production_countries : movie_id
    movies ||--|{ spoken_languages : movie_id
    casts }|--|| actors : actor_id
    crews }|--|| workers : worker_id
    genres }|--|| genres_type : genre_id
    keywords }|--|| keyword_type : keywork_id
    production_companies }|--|| production_company_type : production_company_id
    production_countries }|--|| production_country_type : iso_3166_1
    spoken_languages }|--|| spoken_language_type : iso_639_1
    
    
```

