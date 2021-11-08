<template>
  <Header color="#358d84" />
  <Filters @apply-filters="applyFilters" color="#358d84" />
  <div class="scoreBox">
    <Leagues :leagues="leagues" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Filters from './components/Filters.vue'
import Leagues from './components/Leagues.vue'
export default {
  name: 'App',
  components: {
    Header,
    Filters,
    Leagues
  },
  data(){
    return {
      leagues: [],
      all_leagues: []
    }
  },
  methods: {
    applyFilters(filters){
      //Date Filter
      this.leagues = this.all_leagues.filter((league) => {return league.day == filters.dayFilter})
      //Category Filter
      filters.categoryFilter === 'all' ? null 
      : this.leagues = this.leagues.filter((league)=>{
         return (league.category == filters.categoryFilter);
      })
    }
  },
  created(){
    this.all_leagues = [
	  {
		"id": 1,
		"name": "Coupe De France",
		"day": "yesterday",
    "isFav": false,
		"category": "live",
		"country": {
		  "name": "France",
		  "code": "fr"
		},
		"matches": [
		  {
			"id": 1,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Chambly",
			  "score": 2
			},
			"teamB": {
			  "name": "FC Rouen",
			  "score": 1
			}
		  },
		  {
			"id": 2,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "Ajaccio",
			  "score": 1
			},
			"teamB": {
			  "name": "US Orieans",
			  "score": 2
			}
		  },
		  {
			"id": 3,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Carquefou",
			  "score": 3
			},
			"teamB": {
			  "name": "Tregunc",
			  "score": 2
			}
		  }
		]
	  },
	  {
		"id": 2,
		"name": "Championnat National 2",
		"day": "yesterday",
    "isFav": false,
		"category": "live",
		"country": {
		  "name": "France",
		  "code": "fr"
		},
		"matches": [
		  {
			"id": 1,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Yzeure",
			  "score": 2
			},
			"teamB": {
			  "name": "Andrezzieux",
			  "score": 1
			}
		  },
		  {
			"id": 2,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "FC Rouen",
			  "score": 1
			},
			"teamB": {
			  "name": "US Saint-Malo",
			  "score": 2
			}
		  },
		  {
			"id": 3,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Lyon II",
			  "score": 2
			},
			"teamB": {
			  "name": "Grasse",
			  "score": 2
			}
		  },
		  {
			"id": 4,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Jura Sud",
			  "score": 3
			},
			"teamB": {
			  "name": "SC Lyon",
			  "score": 2
			}
		  }
		]
	  },
	  {
		"id": 3,
		"name": "Tahiti Ligue 1",
		"day": "yesterday",
    "isFav": true,
		"category": "favorites",
		"country": {
		  "name": "France",
		  "code": "fr"
		},
		"matches": [
		  {
			"id": 1,
			"isEnd": true,
			"isPens": false,
			"teamA": {
			  "name": "Pirae",
			  "score": 1
			},
			"teamB": {
			  "name": "Temanava",
			  "score": 2
			}
		  },
		  {
			"id": 2,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "Pueu",
			  "score": 2
			},
			"teamB": {
			  "name": "Olympic Mahina",
			  "score": 2
			}
		  },
		  {
			"id": 3,
			"isEnd": true,
			"isPens": false,
			"teamA": {
			  "name": "Excelsior",
			  "score": 3
			},
			"teamB": {
			  "name": "Dragon",
			  "score": 1
			}
		  },
		  {
			"id": 4,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Jura Sud",
			  "score": 2
			},
			"teamB": {
			  "name": "SC Lyon",
			  "score": 3
			}
		  }
		]
	  },
	  {
		"id": 4,
		"name": "EFL Cup",
		"day": "today",
    "isFav": false,
		"category": "live",
		"country": {
		  "name": "England",
		  "code": "gb"
		},
		"matches": [
		  {
			"id": 1,
			"isEnd": true,
			"isPens": false,
			"teamA": {
			  "name": "Stoke City",
			  "score": 2
			},
			"teamB": {
			  "name": "Brentford",
			  "score": 1
			}
		  },
		  {
			"id": 2,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "West Ham",
			  "score": 2
			},
			"teamB": {
			  "name": "Man City",
			  "score": 3
			}
		  },
		  {
			"id": 3,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Leicester City",
			  "score": 3
			},
			"teamB": {
			  "name": "Brighton",
			  "score": 4
			}
		  },
		  {
			"id": 4,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Arsenal",
			  "score": 1
			},
			"teamB": {
			  "name": "Sunderland",
			  "score": 3
			}
		  }
		]
	  },
	  {
		"id": 5,
		"name": "Premier League",
		"day": "tomorrow",
    "isFav": true,
		"category": "favorites",
		"country": {
		  "name": "England",
		  "code": "gb"
		},
		"matches": [
		  {
			"id": 1,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "West Ham",
			  "score": 3
			},
			"teamB": {
			  "name": "Liverpool",
			  "score": 2
			}
		  },
		  {
			"id": 2,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "Everton",
			  "score": 2
			},
			"teamB": {
			  "name": "Tottenham",
			  "score": 1
			}
		  },
		  {
			"id": 3,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "Leeds United",
			  "score": 1
			},
			"teamB": {
			  "name": "Leicester City",
			  "score": 1
			}
		  },
		  {
			"id": 4,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "Aston Villa",
			  "score": 2
			},
			"teamB": {
			  "name": "Brighton",
			  "score": 4
			}
		  }
		]
	  },
	  {
		"id": 6,
		"name": "EFL Cup",
		"day": "tomorrow",
    "isFav": false,
		"category": "live",
		"country": {
		  "name": "England",
		  "code": "gb"
		},
		"matches": [
		  {
			"id": 1,
			"isEnd": true,
			"isPens": false,
			"teamA": {
			  "name": "Stoke City",
			  "score": 2
			},
			"teamB": {
			  "name": "Brentford",
			  "score": 1
			}
		  },
		  {
			"id": 2,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "West Ham",
			  "score": 2
			},
			"teamB": {
			  "name": "Man City",
			  "score": 3
			}
		  },
		  {
			"id": 3,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Leicester City",
			  "score": 3
			},
			"teamB": {
			  "name": "Brighton",
			  "score": 4
			}
		  },
		  {
			"id": 4,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Arsenal",
			  "score": 1
			},
			"teamB": {
			  "name": "Sunderland",
			  "score": 3
			}
		  }
		]
	  },
	  {
		"id": 7,
		"name": "EFL Cup",
		"day": "today",
    "isFav": true,
		"category": "favorites",
		"country": {
		  "name": "England",
		  "code": "gb"
		},
		"matches": [
		  {
			"id": 1,
			"isEnd": true,
			"isPens": false,
			"teamA": {
			  "name": "Stoke City",
			  "score": 2
			},
			"teamB": {
			  "name": "Brentford",
			  "score": 1
			}
		  },
		  {
			"id": 2,
			"isEnd": false,
			"isPens": false,
			"teamA": {
			  "name": "West Ham",
			  "score": 2
			},
			"teamB": {
			  "name": "Man City",
			  "score": 3
			}
		  },
		  {
			"id": 3,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Leicester City",
			  "score": 3
			},
			"teamB": {
			  "name": "Brighton",
			  "score": 4
			}
		  },
		  {
			"id": 4,
			"isEnd": true,
			"isPens": true,
			"teamA": {
			  "name": "Arsenal",
			  "score": 1
			},
			"teamB": {
			  "name": "Sunderland",
			  "score": 3
			}
		  }
		]
	  }
	];
  this.applyFilters({
    dayFilter: "yesterday",
    categoryFilter: "all"
  })
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  border: none;
  text-decoration: none;
}
body{
  background: #f3f3f4;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.scoreBox{
  padding: 10px;
}
</style>
