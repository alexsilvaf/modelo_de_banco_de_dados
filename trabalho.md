```mermaid
erDiagram
    Filme_e_Serie {
        id 	STRING
        nome STRING
        tipo STRING
        classificacao INTEGER
    }
    Premiacao {
        id INTEGER
        nome STRING
	valor INTEGER
	ano INTEGER
    }
    Premiacao_filme_e_series {
        id INTEGER
        id_premiacao INTEGER
	id_filme STRING
    }
    Streming {
        id INTEGER
        nome STRING
        site STRING
    }
    Filme_e_serie_streming {
        id INTEGER
        id_filmes_e_series STRING
        id_streming STRING
    }
    Ator {
        id INTEGER
        nome STRING
    }
    Ator_Filme_e_serie {
        id INTEGER
        id_ator INTEGER
        id_filme STRING
    }
    Ator_Premiacao {
        id_Preamiacao_Ator INTEGER
        id_Ator INTEGER
        id_Premiacao INTEGER
    }
    

    Filme_e_Serie    	}o--||      Premiacao_filme_e_series        : "recebe"
    Premiacao           }o--||     Premiacao_filme_e_series         : "recompensa"

    Filme_e_Serie       }o--||      Filme_e_serie_streming  	    : "lançado"
    Streming            }o--||      Filme_e_serie_streming          : "exibe"

    Filme_e_Serie       }o--||      Ator_Filme_e_serie              : "contém"
    Ator                }o--||      Ator_Filme_e_serie              : "atua"

    Premiacao           }o--||      Ator_Premiacao                  : "recompensa"
    Ator                }o--||      Ator_Premiacao                  : "recebe"

