require 'fraccionarios'

class Matriz

#-------------------------------------------------------------------------------   
	attr_accessor :filas,:cols, :matriz


#-------------------------------------------------------------------------------   
	def initialize(m) 
		@filas = m.size
		@cols = m[1].size
		@matriz = m
	end	

	def + (other)
	end

	def * (other)
	end

end










class MatrizEntera < Matriz

#Suma matrices enteros
#-------------------------------------------------------------------------------   
	def + (other)
		i=0
 		copia = @matriz
		while i < @filas
			j=0
			while j < @cols
			   copia[i][j] = copia[i][j] + other.matriz[i][j]
				j += 1
			end
			i += 1
		end
		Matriz.new(copia)
	end



#Resta matrices enteros
#-------------------------------------------------------------------------------   
	def - (other)
		i=0
 		copia = @matriz
		while i < @filas
			j=0
			while j < @cols
			   copia[i][j] = copia[i][j] - other.matriz[i][j]
				j += 1
			end
			i += 1
		end
		Matriz.new(copia)
	end


#Multiplicacion matrices enteros
#-------------------------------------------------------------------------------   
	def * (other)
		i=0
 		copia = Array.new(@filas) {Array.new(other.cols,0)}
		while i < @filas
			j=0
			while j < other.cols
				copia[i][j] = 0
				k=0
				while k < @cols 
			   	copia[i][j] = copia[i][j] + (matriz[i][k] * other.matriz[k][j])
					#puts " #{k} #{i}    #{matriz[i][k]}*#{other.matriz[k][j]}"
					k+=1
				end
				j += 1
			end
			i += 1
		end
		Matriz.new(copia)
	end

end











class MatrizRacional < Matriz

#Suma matrices racionales
#-------------------------------------------------------------------------------   
	def + (other)
		i=0
 		copia = @matriz
		while i < @filas
			j=0
			while j < @cols
			   copia[i][j] = (Fraccionario.construccion(copia[i][j]) + Fraccionario.construccion(other.matriz[i][j])).imprimirFraccion
				j += 1
			end
			i += 1
		end
		Matriz.new(copia)
	end




#Multiplicacion de matrices racionales
#-------------------------------------------------------------------------------   
	def * (other)
		i=0
 		copia = Array.new(@filas) {Array.new(other.cols,0)}
		while i < @filas
			j=0
			while j < other.cols
				copia[i][j] = 0
				k=0
				while k < @cols 
			   	copia[i][j] = copia[i][j] + (matriz[i][k] * other.matriz[k][j])
					#puts " #{k} #{i}    #{matriz[i][k]}*#{other.matriz[k][j]}"
					k+=1
				end
				copia[i][j] = (Fraccionario.construccion(copia[i][j])).imprimirFraccion
				j += 1
			end
			i += 1
		end
		Matriz.new(copia)
	end

end
