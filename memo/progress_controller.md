# 質問を表示していく処理
## おおまかな流れ
ゲームが始まり、進行中になる。 \
質問がランダムで表示される。 \
質問に答える。 \
質問が保存される。 \
次の質問を出す。
## 質問を出す
`/game/:game_id/progress/new`
Progressモデルを作成し、 \
game_idをもとに、Gameモデルを取り出す。 \
質問を表示する。
## 質問に答える
`POST /game/:game_id/progress/`
現在のGameと関連付けてProgressモデルに質問への答えを保存する。 \
`/game/:game_id/progress/new`にリダイレクトし新しい質問を出す
## 重複する質問を出さないようにする
現在のGameと関連あるProgressモデルから、question_idを取り出す。 \
このquestion_idを含まない、質問が新規の質問。 \
新規の質問をシャッフルし、一つ取り出す。


