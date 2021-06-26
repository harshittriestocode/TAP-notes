# FE code to

  ## 1. Get data from BE

      const getMovies = async () => {
          setLoader(true);
          const movieData = await axios.get(`http://localhost:4000/movie?title=${search}`);
          setLoader(false);
          if (movieData.data) {
              setError("");
              console.log(movieData.data);
              setMovie(movieData.data);
          } else {
              setError(movies.data["Error"]);
          }
      }

  ## 2. Send data to BE

      const addMovie = async () => {
          setLoader(true);
          const response = await axios({
              url: `http://localhost:4000/movie/add`,
              method: 'post',
              data: {
                  movieId:movieId,
                  name:name,
                  poster:poster
              }
          });
          toggle();
          setLoader(false);
      }
