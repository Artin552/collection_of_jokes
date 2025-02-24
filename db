import sqlite3
connection = sqlite3.connect('Jokes.db')
cursor = connection.cursor()
create_table = '''
CREATE TABLE IF NOT EXISTS Jokes(
    id INTEGER PRIMARY KEY,
    joke TEXT NOT NULL
)
'''

insert_table = '''
INSERT INTO Jokes(id,joke)
VALUES (?,?)
'''

data_table = [
    (1,"Девушки! Если парень останавливает видеоигру, чтобы ответить на ваше сообщение, — выходите за него замуж."),
    (2,"Сейчас нужно очень внимательно переходить дорогу, так как дети, выросшие на GTA, Carmageddon и Need For Speed, начали получать водительские права."),
    (3,"— Подскажите программы для оптимальной расстановки мебели.\
— «Тетрис»."),
    (4,"Благодаря видеоиграм я понимаю, что если встречаю врагов, то, значит, двигаюсь в верном направлении."),
    (5,"Программист, чтобы начать работу, должен сесть за комп, а геймер — встать из-за него."),
    (6,"У геймеров есть только один инстинкт — инстинкт автосохранения.")
]

cursor.execute(create_table)
cursor.executemany(insert_table, data_table)
connection.commit()
connection.close()

