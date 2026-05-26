
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>스피드 영어 퀴즈 (Week 13~16)</title>
    <style>
        body { font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, Roboto, sans-serif; background-color: #f0f4f8; color: #333; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; padding: 20px; box-sizing: border-box; }
        .container { background: white; padding: 30px; border-radius: 16px; box-shadow: 0 10px 30px rgba(0,0,0,0.08); max-width: 650px; width: 100%; }
        h1 { text-align: center; margin-bottom: 20px; color: #1e293b; font-size: 26px; }
        .week-tabs { display: flex; gap: 10px; margin-bottom: 25px; border-bottom: 2px solid #e2e8f0; padding-bottom: 10px; justify-content: center; flex-wrap: wrap; }
        .week-tab { padding: 10px 16px; border: none; background: none; font-size: 15px; font-weight: bold; color: #94a3b8; cursor: pointer; border-radius: 8px; transition: all 0.2s; }
        .week-tab.active { background-color: #e0f2fe; color: #0284c7; }
        .week-tab:hover:not(.active):not(:disabled) { background-color: #f1f5f9; }
        .week-tab:disabled { cursor: not-allowed; opacity: 0.5; }
        .category-section { margin-bottom: 25px; background: #f8fafc; padding: 20px; border-radius: 12px; border: 1px solid #e2e8f0; }
        .category-title { font-size: 18px; font-weight: bold; color: #334155; margin-top: 0; margin-bottom: 15px; display: flex; align-items: center; gap: 8px; }
        .flavor-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
        @media (max-width: 480px) { .flavor-grid { grid-template-columns: 1fr; } }
        .flavor-btn { background: white; border: 2px solid #cbd5e1; border-radius: 10px; padding: 15px; text-align: left; cursor: pointer; transition: all 0.2s ease; }
        .flavor-btn:hover { border-color: #3b82f6; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.15); transform: translateY(-2px); }
        .flavor-title { font-size: 16px; font-weight: bold; display: block; margin-bottom: 6px; }
        .flavor-desc { font-size: 13px; color: #64748b; line-height: 1.4; word-break: keep-all; }
        .t-easy { color: #10b981; } .t-hard { color: #ef4444; }
        .hidden { display: none !important; }
        #quiz-area { display: flex; flex-direction: column; gap: 20px; }
        #question-counter { font-size: 15px; color: #64748b; font-weight: bold; text-align: center;}
        .question-box { font-size: 22px; font-weight: bold; word-break: keep-all; line-height: 1.5; background: #f8fafc; padding: 30px 20px; border-radius: 12px; border: 2px dashed #cbd5e1; cursor: pointer; transition: background 0.2s; text-align: center; }
        .question-box:hover { background: #e2e8f0; }
        .question-box::after { content: "(클릭하여 정답 확인)"; font-size: 13px; color: #94a3b8; display: block; margin-top: 10px; font-weight: normal; }
        .answer-box { background: #ecfdf5; padding: 25px 20px; border-radius: 12px; border: 1px solid #a7f3d0; text-align: left; }
        .en-text { font-size: 22px; color: #059669; font-weight: bold; margin-bottom: 15px; line-height: 1.4; word-break: keep-all;}
        .meta-info { font-size: 14px; color: #475569; margin-bottom: 5px; background: #fff; display: inline-block; padding: 4px 10px; border-radius: 20px; border: 1px solid #e2e8f0; }
        .meaning-info { font-size: 15px; color: #b45309; margin-bottom: 15px; background: #fef3c7; padding: 8px 12px; border-radius: 8px; font-weight: 500;}
        .controls { display: flex; justify-content: space-between; align-items: center; margin-top: 10px; flex-wrap: wrap; gap: 10px;}
        .left-controls { display: flex; gap: 10px; }
        .btn { padding: 10px 20px; border: none; border-radius: 8px; cursor: pointer; font-weight: bold; font-size: 15px; transition: 0.2s;}
        .btn-tts { background-color: #8b5cf6; color: white; display: flex; align-items: center; gap: 5px; }
        .btn-tts:hover { background-color: #7c3aed; }
        .btn-star { background-color: #e2e8f0; color: #475569; }
        .btn-star.active { background-color: #fef08a; color: #ca8a04; border: 1px solid #fde047; }
        .btn-next { background-color: #10b981; color: white; }
        .btn-next:hover { background-color: #059669; }
        .btn-finish { background-color: #3b82f6; color: white; width: 100%; padding: 15px; font-size: 16px; margin-top: 10px; }
        .btn-finish:hover { background-color: #2563eb; }
        .btn-home { background-color: #64748b; color: white; width: 100%; padding: 15px; font-size: 16px; margin-top: 20px;}
        .btn-home:hover { background-color: #475569; }
        #review-area { display: flex; flex-direction: column; gap: 15px; }
        .review-card { background: #fff; border: 1px solid #e2e8f0; border-radius: 10px; padding: 15px; box-shadow: 0 2px 5px rgba(0,0,0,0.05); text-align: left;}
        .review-ko { font-size: 16px; font-weight: bold; color: #334155; margin-bottom: 8px; }
        .review-en { font-size: 18px; font-weight: bold; color: #059669; margin-bottom: 8px; }
        .review-empty { text-align: center; padding: 40px 20px; font-size: 18px; color: #10b981; font-weight: bold; background: #ecfdf5; border-radius: 12px;}
    </style>
</head>
<body>

<div class="container">
    <h1 id="main-title">🚀 스피드 영어 퀴즈</h1>
    <div id="mode-selection">
        <div class="week-tabs">
            <button class="week-tab active" onclick="setWeek(13, this)">Week 13</button>
            <button class="week-tab" disabled>Week 14 (준비중)</button>
            <button class="week-tab" disabled>Week 15 (준비중)</button>
            <button class="week-tab" disabled>Week 16 (준비중)</button>
            <button class="week-tab" onclick="setWeek('all', this)">Week 13~16 누적</button>
        </div>
        <div class="category-section">
            <h3 class="category-title">🧩 구동사 (Phrasal Verbs)</h3>
            <div class="flavor-grid">
                <button class="flavor-btn" onclick="startQuiz('phrasal-easy')"><span class="flavor-title t-easy">🟢 순한맛</span><span class="flavor-desc">구동사 의미별로 짧고 쉬운 문장들이 선별해서 담겨있음</span></button>
                <button class="flavor-btn" onclick="startQuiz('phrasal-hard')"><span class="flavor-title t-hard">🔴 매운맛</span><span class="flavor-desc">전체 예문에서 선별됨</span></button>
            </div>
        </div>
        <div class="category-section">
            <h3 class="category-title">🗣️ 영어회화 (Conversation)</h3>
            <div class="flavor-grid">
                <button class="flavor-btn" onclick="startQuiz('conv-easy')"><span class="flavor-title t-easy">💬 순한맛</span><span class="flavor-desc">'대표문장'과 '교재1'만 담고 있음</span></button>
                <button class="flavor-btn" onclick="startQuiz('conv-hard')"><span class="flavor-title t-hard">🔥 매운맛</span><span class="flavor-desc">전체 예문에서 선별됨</span></button>
            </div>
        </div>
    </div>
    <div id="quiz-area" class="hidden">
        <div id="question-counter">문제 1 / 7</div>
        <div class="question-box" id="ko-box" onclick="showAnswer()"><span id="ko-text">한국어 문장</span></div>
        <div class="answer-box hidden" id="answer-section">
            <div class="meta-info" id="source-info">출처</div>
            <div class="en-text" id="en-text">English Answer</div>
            <div class="meaning-info hidden" id="meaning-info">의미</div>
            <div class="controls">
                <div class="left-controls"><button class="btn btn-tts" onclick="playTTS()">🔊 듣기</button><button class="btn btn-star" id="btn-star" onclick="toggleStar()">⭐ 어려워요</button></div>
                <button class="btn btn-next" id="btn-next" onclick="nextQuestion()">다음 문제 ➡</button>
            </div>
        </div>
        <button class="btn btn-finish hidden" id="btn-finish" onclick="showReview()">결과 보기 (오답 노트) 📝</button>
    </div>
    <div id="review-area" class="hidden">
        <h2 style="text-align: center; color: #1e293b; margin-top:0;">⭐ 나의 오답 노트</h2>
        <p style="text-align: center; color: #64748b; font-size: 14px; margin-top:-10px;">어려웠던 문장들을 다시 확인해 보세요!</p>
        <div id="review-list"></div>
        <button class="btn btn-home" onclick="resetToHome()">🏠 처음으로 돌아가기</button>
    </div>
</div>

<script>
    let currentWeekFilter = 13;
    function setWeek(week, btn) {
        if (week === 'all') currentWeekFilter = 'all';
        else currentWeekFilter = parseInt(week);
        document.querySelectorAll('.week-tab').forEach(el => el.classList.remove('active'));
        btn.classList.add('active');
    }

    // 📌 구동사 Week 13 의미 매핑
    const meanings = {
        "mess around_1": "mess around: (고장 날 위험이 있는 사물을) 자꾸 만지작거리다",
        "mess around_2": "mess around: (해야 할 일을 안 하고) 빈둥거리며 시간을 보내다",
        "mess around_3": "mess around: (진지하지 않게 가벼운 태도로) 장난치다",
        "mess around_4": "mess around: (이성과 진지하지 않은 관계를 맺으며) 시간을 허비하다",
        "mess up_1": "mess up: (실수를 저질러 상황을) 망치다",
        "mess up_2": "mess up: (깔끔했던 것을 지저분하게) 엉망으로 만들다",
        "mess with_1": "mess with: (커피 등이 수면 등에) 안 좋은 영향을 미치다, 방해하다",
        "mess with_2": "mess with: (트러블을 피하기 위해 특정인과) 더는 엮이지 않다",
        "mess with_3": "mess with: (상대를 골탕 먹이려고 장난삼아) 놀리다",
        "mess with_4": "mess with: (남의 물건이나 설정을 부주의하게 만져서) 망가뜨리다",
        "mess with_5": "mess with: (화난 사람을) 괜히 자극하다, 건드리다",
        "miss out_1": "miss out: (남들은 다 누리는) 좋은 기회나 즐거움을 놓치다",
        "move on_1": "move on: (한 장소에서 머물다가 다른 장소로) 이동하다",
        "move on_2": "move on: (하던 일을 마치고 다음 단계/질문으로) 넘어가다",
        "move on_3": "move on: (이별 후 상처를 잊고) 새로운 출발을 하다",
        "move on_4": "move on: (과거의 팬이나 지지자가) 이미 마음이 떠나버리다"
    };

    // 1. 구동사 순한맛 (Week 13)
    const phrasalEasy = [
        { week: 13, ko: "휴대폰 그만 만지작거려.", en: "Stop messing around with your phone.", source: "Day 061 순한맛", meaning: meanings["mess around_1"] },
        { week: 13, ko: "비디오 게임을 하면서 계속 빈둥거리네요.", en: "My son keeps messing around with video games when he should be studying for his exams.", source: "Day 061 순한맛", meaning: meanings["mess around_2"] },
        { week: 13, ko: "그냥 장난친 거라고.", en: "I was just trying to mess around.", source: "Day 061 순한맛", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 여러 이성을 만나는 것도 지겹습니다.", en: "I am tired of messing around.", source: "Day 061 순한맛", meaning: meanings["mess around_4"] },
        { week: 13, ko: "공연 때 대사 몇 개를 잘못 말했지 뭐야.", en: "During the play, I messed up several of my lines.", source: "Day 062 순한맛", meaning: meanings["mess up_1"] },
        { week: 13, ko: "그가 취소하는 바람에 제 스케줄 전체가 꼬여 버렸습니다.", en: "His cancellation has messed up my whole schedule.", source: "Day 062 순한맛", meaning: meanings["mess up_2"] },
        { week: 13, ko: "늦은 시간에 커피 마시지 말아야겠어; 수면에 방해가 돼.", en: "I have to stop drinking coffee late; it messes with my sleep.", source: "Day 063 순한맛", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 Brandon이랑은 엮이기 싫어.", en: "I don’t mess with Brandon anymore.", source: "Day 063 순한맛", meaning: meanings["mess with_2"] },
        { week: 13, ko: "그냥 한 말이야.", en: "I was just messing with you.", source: "Day 063 순한맛", meaning: meanings["mess with_3"] },
        { week: 13, ko: "이봐, 내 카메라 설정 건드린 거야?", en: "Hey, did you mess with the settings on my camera?", source: "Day 063 순한맛", meaning: meanings["mess with_4"] },
        { week: 13, ko: "주방에 있는 분은 건드리면 안 된다는 걸 알게 되었어요.", en: "I learned the hard way not to mess with kitchen staff.", source: "Day 063 순한맛", meaning: meanings["mess with_5"] },
        { week: 13, ko: "이건 너무 중요한 기회야! 절대로 그냥 보내지 않을 거야.", en: "This is a huge chance! I’m not going to miss out on it.", source: "Day 064 순한맛", meaning: meanings["miss out_1"] },
        { week: 13, ko: "저녁 먹고, 조용한 와인바로 이동해서 몇 시간 동안 이야기를 나누었어.", en: "We had dinner and moved on to a quiet wine bar where we talked for hours.", source: "Day 065 순한맛", meaning: meanings["move on_1"] },
        { week: 13, ko: "답을 모르겠으면, 다음 문제로 넘어갔다가 다시 풀어 봐.", en: "Move on and try again when you’ve finished the easier ones.", source: "Day 065 순한맛", meaning: meanings["move on_2"] },
        { week: 13, ko: "전 남자 친구를 굉장히 빨리 잊는 것 같아.", en: "I guess she moves on really fast.", source: "Day 065 순한맛", meaning: meanings["move on_3"] },
        { week: 13, ko: "스캔들 이후에 그의 팬 중 많은 이들의 마음이 이미 떠난 상태다.", en: "Following the scandal, many of his fans have already moved on.", source: "Day 065 순한맛", meaning: meanings["move on_4"] }
    ];

    // 2. 구동사 매운맛 (Week 13)
    const phrasalHard = [
        { week: 13, ko: "아빠가 쓰는 공구들 가지고 장난 그만 좀 쳐! 위험한 것들이 있단 말이야.", en: "Don’t mess around with your dad’s tools! Some of them are dangerous.", source: "Day 061 교재1", meaning: meanings["mess around_1"] },
        { week: 13, ko: "제가 음악가는 아니지만 시간이 날 때면 드럼을 가지고 노는 걸 좋아합니다.", en: "I’m not a musician, but I like to mess around with the drums when I can.", source: "Day 061 교재1", meaning: meanings["mess around_1"] },
        { week: 13, ko: "오후 내내 보고서 마무리는 안 하고 휴대폰 하는 데 시간을 허비했다.", en: "I spent the whole afternoon messing around with my phone instead of finishing my report.", source: "Day 061 교재1", meaning: meanings["mess around_2"] },
        { week: 13, ko: "미안해. (네) 기분 상하게 할 의도는 없었어. 그냥 장난친 거라고.", en: "I’m sorry. I didn’t mean for you to take that as an insult. I was just trying to mess around.", source: "Day 061 교재1", meaning: meanings["mess around_3"] },
        { week: 13, ko: "그 둘은 그냥 재미로 만나는 거야. 둘 다 당장은 사귄다는 걸 알릴 마음이 없어.", en: "They’re just messing around; neither of them is planning on making it official anytime soon.", source: "Day 061 교재1", meaning: meanings["mess around_4"] },
        { week: 13, ko: "휴대폰 그만 만지작거려. 이제 자러 가야 할 시간이야.", en: "Stop messing around with your phone. It’s time to go to bed.", source: "Day 061 교재1", meaning: meanings["mess around_1"] },
        { week: 13, ko: "제 아들이 시험공부를 해야 함에도 비디오 게임을 하면서 계속 빈둥거리네요.", en: "My son keeps messing around with video games when he should be studying for his exams.", source: "Day 061 교재1", meaning: meanings["mess around_2"] },
        { week: 13, ko: "Andrew, 동생 좀 그만 놀리렴. 또 한 번 울리면 아빠한테 이른다.", en: "Stop messing around with your brother, Andrew. If you make him cry again, I’m telling your dad.", source: "Day 061 교재1", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 여러 이성을 만나는 것도 지겹습니다. 정착해서 몇 년 안에 결혼하고 싶네요.", en: "I am tired of messing around. I want to settle down and get married within the next few years.", source: "Day 061 교재1", meaning: meanings["mess around_4"] },
        { week: 13, ko: "너희들 그룹 프로젝트 마무리하는 데 얼마나 걸렸어?", en: "How long did it take for you guys to finish the group project?", source: "Day 061 교재2", meaning: null },
        { week: 13, ko: "10시간 정도. 근데 계속해서 작업을 한 건 아니야. 끝나갈 무렵에는 슬슬 놀면서 했어.", en: "About 10 hours, but it wasn’t like we were working the whole time. Near the end, we were pretty much just messing around.", source: "Day 061 교재2", meaning: meanings["mess around_2"] },
        { week: 13, ko: "정말 이 머리 스타일 나한테 안 어울리는 거 같아? 여자 친구는 귀엽다고 했거든.", en: "Do you really think this hairstyle looks bad on me? My girlfriend said it looks cute.", source: "Day 061 교재2", meaning: null },
        { week: 13, ko: "아니야. 그냥 농담한 거야. 귀여워.", en: "No. I was just messing around. It’s cute.", source: "Day 061 교재2", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 더 이상 이런 연애 안 할래. 나랑 결혼 안 할 거면 우리 끝내자.", en: "I am done messing around. If you are not going to marry me, then we are through.", source: "Day 061 교재2", meaning: meanings["mess around_4"] },
        { week: 13, ko: "내가 결혼을 원하지 않는다고 해서 집중을 안 하는 건 아니잖아. 결혼하지 않고도 서로에게 충실할 수는 없을까?", en: "Just because I don’t want to get married, that doesn’t mean I’m messing around. Can’t we be committed to each other without making things official?", source: "Day 061 교재2", meaning: meanings["mess around_4"] },
        { week: 13, ko: "자, 이제 신년도 되었으니 나쁜 습관 세 가지를 고치기로 결심했다.", en: "Well, it’s the start of a new year, and I’ve decided to work on three of my bad habits.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "우선 나는 회사에 제시간에 출근하는 것을 정말 못한다.", en: "First of all, I’m terrible at getting to work on time.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "늦는 경우가 많아서 이 때문에 여러 번 지적을 받았다.", en: "I’m usually late and have been reprimanded multiple times because of it.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "솔직히 출근하기가 너무 싫어서 출근 전에 30분 정도 뭉그적거리는 버릇이 있다.", en: "Honestly, before leaving for work, I tend to mess around for like 30 minutes because I just don’t want to go.", source: "Day 061 교재3", meaning: meanings["mess around_2"] },
        { week: 13, ko: "두 번째로 여가 시간을 좀 더 효과적으로 보낼 필요가 있다.", en: "Second, I need to use my free time more effectively.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "최근에는 퇴근 후에 아무 생각 없이 유튜브를 보거나 SNS를 하게 된다.", en: "Lately, when I get home from work, I just end up mindlessly watching YouTube or checking social media.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "이런 무의미한 시간을 좀 더 나은 사람이 될 수 있는 취미에 쓰면 더 좋다는 것을 알고 있다. 하지만 노력을 해도 잘 안된다.", en: "I know my time could be better spent on hobbies that make me a better person, but I just can’t get myself to do them.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "마지막으로 제때 취침을 해야겠다.", en: "Last, I’m going to start going to bed on time.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "수면 부족으로 건강이 나빠지고 있다.", en: "A lack of sleep has been taking a toll on my health.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "공연 때 대사 몇 개를 잘못 말했지 뭐야.", en: "During the play, I messed up several of my lines.", source: "Day 062 교재1", meaning: meanings["mess up_1"] },
        { week: 13, ko: "올림픽에서는 설사 실수를 하더라도 아무 일 없었다는 듯 행동해야 해.", en: "When you mess up in the Olympics, you’re supposed to act gracefully about it.", source: "Day 062 교재1", meaning: meanings["mess up_1"] },
        { week: 13, ko: "내가 제일 좋아하는 음식이 프라이드치킨인데, 먹을 때마다 속이 뒤집어진다는 점이 문제야.", en: "My favorite food is fried chicken, but it messes up my stomach every time.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "연습하는 동안 계속 이 춤 동작을 실수하게 된다. 이번 주말 무대에서도 내가 실수할까 봐 우리 팀원들이 걱정하고 있다.", en: "I keep messing up this particular dance move during practice. My team is getting worried that I might mess up on stage this weekend, too.", source: "Day 062 교재1", meaning: meanings["mess up_1"] },
        { week: 13, ko: "내 머리 좀 만지지 마. (자꾸 만지면) 엉망이 될 거야. 아침에 20분이나 들여서 머리 예쁘게 만졌단 말이야.", en: "Stop touching my hair. You are gonna mess it up. I spent 20 minutes this morning getting it just right.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "그가 취소하는 바람에 제 스케줄 전체가 꼬여 버렸습니다.", en: "His cancellation has messed up my whole schedule.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "예상치 못한 일이 생겨 일상이 꼬이는 건 싫다.", en: "I don’t like when unexpected things mess up my routine.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "Nick, 나 실수한 것 같아. 여자 친구에게 내 폰을 보여 주고 있는데, 다른 여자가 내게 메시지를 보냈어.", en: "Nick, I think I messed up. While I was letting my girlfriend look at my phone, another girl messaged me.", source: "Day 062 교재2", meaning: meanings["mess up_1"] },
        { week: 13, ko: "버너폰을 가지고 다녀야 한다고 내가 말했잖아!", en: "I told you to carry a burner phone!", source: "Day 062 교재2", meaning: null },
        { week: 13, ko: "생일이라고 해서 케이크를 만들어 주려 하다가, 베이킹파우더를 너무 많이 넣는 바람에 망쳤네요.", en: "I tried to make you a cake for your birthday, but I messed it up by putting in too much baking powder.", source: "Day 062 교재2", meaning: meanings["mess up_1"] },
        { week: 13, ko: "그래도 만들어 주려고 한 게 정말 고맙군요. 이 케이크 너무 “고마워서” 먹을 수가 없네요. 대신 아이스크림 먹으러 가요.", en: "How sweet of you for trying, though. I “appreciate” this cake too much to eat it. Let’s go get ice cream, instead.", source: "Day 062 교재2", meaning: null },
        { week: 13, ko: "아메리카노 사 왔어.", en: "I bought you an Americano.", source: "Day 062 교재2", meaning: null },
        { week: 13, ko: "아, 미안해. 나 커피 마시면 안 돼. 커피를 안 좋아하는 게 아니고, 카페인을 섭취하면 머리가 아프거든.", en: "Oh, I’m sorry. I can’t have any coffee. It’s not that I don’t like coffee. It’s just that caffeine messes me up.", source: "Day 062 교재2", meaning: meanings["mess up_2"] },
        { week: 13, ko: "나는 해외여행을 할 때 시차 때문에 힘든 일이 잘 없다.", en: "I normally don’t suffer from jet lag when I travel abroad.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "이유는 잘 모르겠지만, 아마 다른 나라에 간다는 게 너무 설레서일지도 모르겠다.", en: "I’m not sure why, though; maybe because I’m always excited to be in a different country.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "하지만 지난달 사장님으로부터 업무 회의차 토론토 출장을 가야 한다는 말을 들었고, 그날 밤 바로 출발해야 한다고 했다.", en: "However, last month I was told by my boss that I needed to fly to Toronto for a business conference, and that I would need to leave that night.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "회의 준비는커녕 집에 가서 짐을 챙길 시간도 거의 없었다.", en: "I barely had time to go home and pack, let alone prepare for business meetings.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "4일 동안 토론토에 있었고 회의는 잘 끝났지만, 출장에서 돌아온 후 계속 수면이 엉망인 상태가 이어지고 있다.", en: "I was there for four days and the meetings went fine, but my sleep has been messed up ever since I got back.", source: "Day 062 교재3", meaning: meanings["mess up_2"] },
        { week: 13, ko: "음악 좀 바꿔 줄래? 기분이 우울해지잖아.", en: "Can you change the music? It’s messing with my mood.", source: "Day 063 교재1", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 Brandon이랑은 엮이기 싫어(안 놀아). 내 화를 돋워 싸움을 시작하게 하는 말만 한다니까.", en: "I don’t mess with Brandon anymore. He knows exactly what to say to rile me up and start a fight.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "저는 출근할 때 더 이상 버스는 안 탑니다. 예측이 어렵고 (버스 타서) 지각한 적이 너무 많습니다.", en: "I don’t mess with the bus system anymore to get to work. It’s unpredictable and it made me late too many times.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "그냥 한 말이야. 너무 예민하게 굴지 마.", en: "I was just messing with you. Don’t be so sensitive.", source: "Day 063 교재1", meaning: meanings["mess with_3"] },
        { week: 13, ko: "이봐, 내 카메라 설정 건드린 거야? 새로 찍은 사진이 죄다 과다 노출로 나오잖아.", en: "Hey, did you mess with the settings on my camera? All my new photos are overexposed.", source: "Day 063 교재1", meaning: meanings["mess with_4"] },
        { week: 13, ko: "늦은 시간에 커피 마시지 말아야겠어. 수면에 방해가 돼.", en: "I have to stop drinking coffee late; it messes with my sleep.", source: "Day 063 교재1", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 술은 안 마십니다. 술 마셔서 좋을 게 하나도 없는 것 같아서요.", en: "I don’t mess with alcohol anymore. It just seems like nothing good ever comes out of drinking.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "식중독 걸린 이후로는 여행 중에 길거리 음식은 안 먹습니다.", en: "Ever since I got food poisoning, I don’t mess with street food on my travels.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "제 친구는 자기가 일본인인 양 메뉴판을 읽지 못하는 척하면서 식당 직원을 골탕 먹이는 버릇이 있습니다. 멍청한 녀석이죠.", en: "My friend likes to mess with servers by pretending he’s Japanese and can’t read the menu. He’s kind of a jerk.", source: "Day 063 교재1", meaning: meanings["mess with_3"] },
        { week: 13, ko: "내가 나가 있는 동안 누가 내 태블릿 건드린 거야? 내가 다운 받지도 않은 앱이 엄청 있네.", en: "Who messed with my new tablet while I was gone? There’s a bunch of apps that I didn’t download on it.", source: "Day 063 교재1", meaning: meanings["mess with_4"] },
        { week: 13, ko: "주방에 있는 분은 건드리면 안 된다는 걸 비싼 대가를 치르고 알게 되었어요. 다음 날 식중독으로 병원 신세를 지게 되었습니다.", en: "I learned the hard way not to mess with kitchen staff. I ended up in the hospital with food poisoning the next day.", source: "Day 063 교재1", meaning: meanings["mess with_5"] },
        { week: 13, ko: "다음 …시에 …하자, …알았지?", en: "Let’s… at… o’clock… next… okay?", source: "Day 063 교재2", meaning: null },
        { week: 13, ko: "뭐라고? 끊겨서 들려. 지하라서 신호가 끊기는 것 같아. 내려서 다시 전화할게.", en: "Sorry? You’re breaking up. I think being underground is messing with my signal. I’ll call you back when I get off.", source: "Day 063 교재2", meaning: meanings["mess with_1"] },
        { week: 13, ko: "내일 만우절이라 학생들 좀 골탕 먹이려고요.", en: "I am going to mess with my students tomorrow for April Fool’s Day.", source: "Day 063 교재2", meaning: meanings["mess with_3"] },
        { week: 13, ko: "진짜요? 어떤 계획인가요? 저도 같이 아이들 놀려 볼까 싶네요.", en: "Oh really? What do you have planned? Maybe I’ll get in on it with you.", source: "Day 063 교재2", meaning: null },
        { week: 13, ko: "Johnny가 뭐라고 했는지 들었어? 누가 걔 좀 혼내 줘야 해.", en: "Did you hear what Johnny said? Someone should teach him a lesson.", source: "Day 063 교재2", meaning: null },
        { week: 13, ko: "걔는 건들지 마. 이 동네에서 제일 센 녀석들이랑 친구니까.", en: "Don’t mess with him. He’s friends with some of the strongest guys in town.", source: "Day 063 교재2", meaning: meanings["mess with_5"] },
        { week: 13, ko: "안녕하세요, 여러분! 오 박사님이 오늘 함께 해 주셨습니다. 알코올 섭취와 과음의 기준에 대해 한 말씀해 주실 겁니다. 박사님, 시작하시죠.", en: "Hello, everyone! Dr. Oh is with us today to teach us a bit about alcohol consumption, and how much is too much. Doctor, please go ahead.", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "감사합니다. 아시다시피 많은 한국인이 퇴근 후 술 한잔하면서 긴장을 푸는 것을 좋아하지만, 문제는 말씀하신 것처럼, 어느 정도가 과한 것일까요?", en: "Thank you. As we all know, a lot of Koreans like to kick back with a few drinks after getting off work, but the question is, as you said, how much is too much?", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "사실 술은 조금만 마신다고 해도 너무 자주 마실 경우에는 건강에 해롭습니다.", en: "Actually, consuming even a little alcohol too frequently can have negative effects on our health.", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "우선 수면의 질을 떨어뜨립니다.", en: "First and foremost, alcohol really messes with your quality of sleep.", source: "Day 063 교재3", meaning: meanings["mess with_1"] },
        { week: 13, ko: "술을 먹어야겠다면 주 1회로 제한해야 하고, 적당히 마셔야 합니다.", en: "If you feel the need to indulge, you should limit yourself to drinking once a week, and in moderation.", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "오늘 밤에 나와. 파티 안 가면 후회할 거야.", en: "Hey, come out tonight. You don’t want to miss the party.", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "A: 아파서 지난 주말 콘서트에 못 갔다며. 맞아?", en: "A: I heard you were sick and couldn’t make it to the concert last weekend. Is that right?", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "B: 응. 정말 가고 싶었는데 전날 독감에 걸렸어.", en: "B: Yeah. I was really looking forward to it, but I got the flu the day before.", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "A: 정말 안됐다! 너무 좋은 기회를 놓쳤네! 정말 멋진 시간이었는데.", en: "A: Too bad! You really missed out! It was an amazing time.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "지민 씨, 토요일 회의하기 전에 아팠다면서요. 걱정 마세요. (회의 때) 이렇다 할 특별한 내용은 없었어요.", en: "Hey Jimin, I heard you got sick before Saturday’s meeting. Don’t worry. You didn’t miss out on anything.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "파티를 즐길 수 있는 기회 혹은 상사랑 술 마실 수 있는 기회를 놓치고 싶지 않거든.", en: "I don’t want to miss out on the party or on getting to drink with the boss.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "A: 우리 가족들이 하와이에 가는데, 나는 일이 바쁘다고 했어.", en: "A: My family is going to Hawaii, but I told them I was too busy at work.", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "B: 뭐라고? 하와이 여행을 마다하는 게 말이 돼?", en: "B: What? Why would you want to miss out on a trip to Hawaii?", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "이건 너무 중요한 기회야! 절대로 그냥 보내지 않을 거야.", en: "This is a huge chance! I’m not going to miss out on it.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "아파서 스키 여행 갈 수 있는 기회를 놓치다니. 너무 속상해!", en: "I can’t believe I missed out on the ski trip because I was sick. What a bummer!", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "도산대로에서 하는 Montana Choi의 파티에 꼭 와. 인맥을 쌓을 수 있는 기회를 놓치면 안 되니까.", en: "You have to come to Montana Choi’s party on Dosan Street. You don’t want to miss out on a chance to network.", source: "Day 064 교재2", meaning: meanings["miss out_1"] },
        { week: 13, ko: "알아. 나도 꼭 가서 그분과 친해지고 싶었어. 근데 내 스케줄을 확실히 모르겠어. 수요일까지 알려줘도 돼?", en: "I know. I was really hoping to go and get acquainted with him. I’m still not sure about my schedule, though. Can I let you know by Wednesday?", source: "Day 064 교재2", meaning: null },
        { week: 13, ko: "회식은 나랑 안 맞아. 상사가 소주를 강요하는 게 너무 싫거든.", en: "Team dinners aren’t really for me. I don’t like that supervisors insist on me drinking soju.", source: "Day 064 교재2", meaning: null },
        { week: 13, ko: "나도 마찬가지야. 나도 회사 회식 가는 거 싫어. 그래도 흥미로운 소소한 이야기를 놓치고 싶지 않아서 여전히 가긴 해.", en: "Same here. I don’t like going out to company dinners, either. But I still go because I don’t want to miss out on the juicy small talk.", source: "Day 064 교재2", meaning: meanings["miss out_1"] },
        { week: 13, ko: "못 오실 줄 알았더니 오셔서 다행입니다. (이번 행사를) 꼭 경험하시길 바랐거든요. 멋진 안경도 보시고 패션 쪽 사람들과도 어울릴 좋은 기회일 거예요.", en: "Well, I’m glad you could make it. I didn’t want you to miss out. It will be a good chance to check out these amazing glasses and mingle with people in the fashion industry.", source: "Day 064 교재2", meaning: meanings["miss out_1"] },
        { week: 13, ko: "팝업 행사 초대해 줘서 고맙습니다. 진짜 기대했습니다. 그나저나 안경테 추천해 주실 만한 것 있을까요?", en: "Thanks for inviting me to the pop-up event. I was really looking forward to it. Are there any particular frames you would recommend, by the way?", source: "Day 064 교재2", meaning: null },
        { week: 13, ko: "아무래도 SNS를 완전히 끊어야 할 것 같다. 특히 인스타그램을 말이다.", en: "I feel like I should quit social media altogether, especially Instagram.", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "친구들이 끊임없이 휴가를 보내거나 밤에 나가서 노는 걸 보면 다른 사람들은 인생을 충분히 즐기는데 나만 소외된 느낌이 든다.", en: "Seeing my friends constantly on holiday or enjoying nights out can make me feel like I am missing out while others are living their life to the fullest.", source: "Day 064 교재3", meaning: meanings["miss out_1"] },
        { week: 13, ko: "최근 우연히 보게 된 기사를 한번 보자.", en: "Take a look at this article I recently came across.", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "내용은 이렇다. “SNS는 사람들에게 비현실적인 기대를 갖게 하고, 자존감이 낮아지게 만든다. 인스타그램 때문에 여성들이 자신의 외모가 부족하다고 느끼게 된다.”", en: "It goes like this: “Social media posts can also set unrealistic expectations and create feelings of low self-esteem. Instagram easily makes girls and women feel as if their bodies aren’t good enough.”", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "여성으로서 이 기사에서 여자가 한 말에 너무 공감이 간다. 여러분은 어떤가?", en: "As a woman, I couldn’t agree more with what she said in the article. How do you feel?", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "A: Haley, 어젯밤 데이트는 어땠어?", en: "A: Haley, how was your date last night?", source: "Day 065 교재1", meaning: null },
        { week: 13, ko: "B: 너무 좋았어. 저녁 먹고, 조용한 와인바로 이동해서 몇 시간 동안 이야기를 나누었어. 이 남자가 내가 찾던 남자라는 생각이 들어.", en: "B: It was amazing. We had dinner and moved on to a quiet wine bar where we talked for hours. I really think this guy is the one.", source: "Day 065 교재1", meaning: meanings["move on_1"] },
        { week: 13, ko: "지하철에서 우연히 전 여자 친구를 마주쳤는데도 아무렇지도 않더군요. 그제서야 이제는 잊고 새출발해도 되겠구나 싶었습니다.", en: "I knew I was ready to move on when I ran into my ex on the subway and I felt completely normal around her.", source: "Day 065 교재1", meaning: meanings["move on_3"] },
        { week: 13, ko: "저는 하나의 업무를 완료하지 못하면 다음 일로 넘어가지 못하는 사람입니다. 멀티태스킹에 능한 사람이 아닙니다.", en: "I’m the kind of person who can’t move on until I completely finish a task. I’m not a multi-tasker.", source: "Day 065 교재1", meaning: meanings["move on_2"] },
        { week: 13, ko: "뉴욕에 3년 살았는데, 정말 좋은 경험이었습니다. 하지만 이젠 다른 도시에 가서 살 때가 된 것 같아요.", en: "I’ve lived in New York for three years and I’m really glad for the experience. But now, I think I am ready to move on.", source: "Day 065 교재1", meaning: meanings["move on_3"] },
        { week: 13, ko: "답을 모르겠으면, 다음 문제로 넘어갔다가 쉬운 것을 다 풀고 난 후에 다시 풀어 봐.", en: "When you don’t know the answer to a question, move on and try again when you’ve finished the easier ones.", source: "Day 065 교재1", meaning: meanings["move on_2"] },
        { week: 13, ko: "Sarah가 이번 주말에 소개팅하기로 했어. 전 남자 친구를 굉장히 빨리 잊는 것 같아.", en: "Sarah’s going on a blind date this weekend. I guess she moves on really fast.", source: "Day 065 교재1", meaning: meanings["move on_3"] },
        { week: 13, ko: "스캔들 이후에 그의 팬 중 많은 이들의 마음이 이미 떠난 상태다.", en: "Following the scandal, many of his fans have already moved on.", source: "Day 065 교재1", meaning: meanings["move on_4"] },
        { week: 13, ko: "이제 다음으로 넘어가도 될 것 같네요. 다음 슬라이드 띄우겠습니다.", en: "I think we’re ready to move on, so I’ll just pull up the next slide.", source: "Day 065 교재2", meaning: meanings["move on_2"] },
        { week: 13, ko: "잠시만요. 배터리 셀 부분을 좀 더 자세히 설명해 주실 수 있을까요? 그 부분이 조금 이해가 안 돼서요.", en: "Wait a second. Can you elaborate more on battery cells? You lost me a bit there.", source: "Day 065 교재2", meaning: null },
        { week: 13, ko: "어젯밤에 Jeff랑 Hailey를 데리고 나가서 저녁 식사했다면서? 어땠어? 오늘 아침에 보니 Jeff 몰골이 말이 아니던데.", en: "I heard you took Jeff and Hailey out to dinner last night. How did it go? Jeff was looking pretty rough this morning when I saw him.", source: "Day 065 교재2", meaning: null },
        { week: 13, ko: "응, 맞아. 1차로 삼겹살 먹고 2차는 공덕역에 있는 ‘언포게터블’이라는 바에 갔어. Jeff가 고주망태가 되어 여자들에게 추파를 던지기 전까지는 좋았는데 말이야. Hailey는 엄청 화가 났지.", en: "Yeah, I did. We first went out for pork belly before moving on to a bar named “Unforgettable” at Gongdeok station. We were having a good time until Jeff got totally wasted and started hitting on some women. Hailey was furious.", source: "Day 065 교재2", meaning: meanings["move on_1"] },
        { week: 13, ko: "아직 지원이에게 감정이 남아 있는 거니? 벌써 6개월이 지났잖아. 과거에 연연하지 말고 새출발해야지.", en: "Are you still upset about Jiwon? It’s been six months already. You can’t let the past get in the way. It’s time to move on.", source: "Day 065 교재2", meaning: meanings["move on_3"] },
        { week: 13, ko: "그게 말처럼 쉽지가 않아. 그녀를 잊을 수가 없어. 헤어진 건 너무 큰 실수였다는 생각 밖에 안 들어.", en: "I wish it was that easy. I can’t get over her. All I can think about is what a huge mistake I made.", source: "Day 065 교재2", meaning: null },
        { week: 13, ko: "예전에는 Lady Gaga의 엄청난 팬이었다. 하지만 최근 앨범은 그냥 쉽게 돈 벌려고 만든 느낌이다.", en: "I used to be a huge fan of Lady Gaga, but her latest album just feels like a cash grab.", source: "Day 065 교재3", meaning: null },
        { week: 13, ko: "이제 그녀의 전성기는 끝난 것 같다. 왜 많은 팬들이 마음이 떠나고 있는지 알겠다.", en: "It looks like her peak time in the spotlight is over, and I can see why many fans are moving on.", source: "Day 065 교재3", meaning: meanings["move on_4"] },
        { week: 13, ko: "그녀는 더 이상 음악계에서 의미 있는 역할을 하지 못하는 듯하다.", en: "She just doesn’t seem to play a real role in the music scene anymore.", source: "Day 065 교재3", meaning: null },
        { week: 13, ko: "팬들과도 너무 동떨어져 있는 것 같다. 특히 SNS에서의 적극적인 활동이 너무 부족하다.", en: "It seems like she’s lost touch with fans, especially with her lack of engagement on social media.", source: "Day 065 교재3", meaning: null },
        { week: 13, ko: "최근에는 예술적인 완성도를 유지하기보다는 돈 버는 데 더 집중하는 것 같아서, 정말 실망스럽다.", en: "Lately, it feels like she’s more focused on making money than maintaining her artistic integrity, which has really disappointed me.", source: "Day 065 교재3", meaning: null }
    ];

    // 3. 영어회화 데이터 (Week 13)
    const rawConvData = [
        { week: 13, source: "Day061 교재1", ko: "미안한데 잘 못 들었어요. 한 번만 더 이야기해 주시겠어요?", en: "Oh, I’m sorry. I didn’t catch that. Could you repeat it?" },
        { week: 13, source: "Day061 교재1", ko: "성함을 못 들은 것 같습니다.", en: "I’m afraid I didn’t catch your name." },
        { week: 13, source: "Day061 교재1", ko: "(이사한다는 말을 듣고) 날짜를 잘 못 들었어. 언제 다시 이사 간다고?", en: "I didn’t catch the date. When are you moving out again?" },
        { week: 13, source: "Day061 교재1", ko: "(발표자가 청중에게) 혹시 놓친 부분이 있을까요?", en: "Is there anything you weren’t able to catch?" },
        { week: 13, source: "Day061 교재1", ko: "예산에 관해 이야기하실 때 제가 발표 내용 일부를 놓쳤어요.", en: "I didn’t catch the part of your presentation when you talked about the budget." },
        { week: 13, source: "Day061 교재2", ko: "안녕하세요, 38 사이즈로 새 신발 있는지 문의드려요.", en: "Hello, I was wondering if you have the new shoes in size 38." },
        { week: 13, source: "Day061 교재2", ko: "죄송한데, 무슨 사이즈라고요? 잘 못 들었어요.", en: "I’m sorry? What size? I didn’t catch that." },
        { week: 13, source: "Day061 교재2", ko: "두 번째 책 제목이 뭐라고 했나요? 저희 집 고양이가 뭘 넘어뜨리는 바람에 못 들었어요.", en: "What did you say was the title of your second book? I didn’t catch that because my cat knocked something over." },
        { week: 13, source: "Day061 교재2", ko: "하하, 괜찮아요. 제 책에 관심 가져 주시는 것만으로도 좋은데요.", en: "Haha, no problem. I’m just glad you’re interested in my work." },
        { week: 13, source: "Day061 교재2", ko: "죄송한데, Kline 선생님? 3, 4번 문제 답을 못 들었어요.", en: "Excuse me, Mr. Kline? I didn’t catch the answers to numbers 3 and 4." },
        { week: 13, source: "Day061 교재2", ko: "아, 그래. 다시 불러 줄게.", en: "Ah, okay. I’ll give the answers again." },
        { week: 13, source: "Day061 교재3", ko: "(줌 회의 진행자가 참석자들에게)\n죄송한데 하시는 말씀이 잘 안 들립니다. 다들 회의 참여 전에 마이크가 되는지 꼭 확인 부탁드립니다. 다시 한번 말씀드리지만 뭘 드시거나 마시면 안 됩니다. 주의가 산만해질 수 있으니까요. 마지막으로, 반려동물이나 아이들은 다른 방에 두시는 것도 잊지 마세요.", en: "I’m sorry. I can’t catch what you’re saying. Everyone, please make sure that your mics are working before entering the meeting. As a reminder, you’re not supposed to eat or drink anything. That can be quite distracting. Finally, please make sure to keep your pets and children in another room." },
        { week: 13, source: "Day061 교재4", ko: "다시 한번 말씀해 주시겠어요? 소음 때문에 잘 못 들었어요.", en: "Could you say that again? I couldn’t quite make you out over all the noise." },
        { week: 13, source: "Day061 교재4", ko: "대충 들리는 말로는, 우리 기차가 10분 정도 늦게 대전역에 도착한다고 하네.", en: "From what I could make out, our train will get to Daejeon station maybe 10 minutes late." },
        { week: 13, source: "Day061 교재4", ko: "동양인들에게는 (미국식과는 다른) 영국식 억양이 알아듣기 힘들 수 있어요.", en: "For Asians, the different British accents can be hard to make out." },
        { week: 13, source: "Day061 대표", ko: "죄송해요. 못 들었어요.", en: "I’m sorry. I didn’t catch that." },
        { week: 13, source: "Day062 교재1", ko: "당신 어제 새벽 3시나 되어서 집에 들어온 데다, 술 냄새가 진동하더군. 오늘 아픈 게 당연한 거야.", en: "You didn’t get home until 3 a.m., and you reeked of alcohol. No wonder you feel sick today." },
        { week: 13, source: "Day062 교재1", ko: "너희 동네에서 시위가 있었다고 뉴스에서 들었어. 그래서 늦었구나.", en: "I heard on the news that there was a protest in your neighborhood. No wonder you’re late." },
        { week: 13, source: "Day062 교재1", ko: "그 사람은 패션 감각이 전혀 없어요. 그러니까 여자 친구가 안 생기죠.", en: "He has zero fashion sense. No wonder he can’t find a girlfriend." },
        { week: 13, source: "Day062 교재1", ko: "공급망 문제가 있으니, 가격이 올라가는 건 당연하죠.", en: "There’s a supply chain issue, so no wonder prices are rising." },
        { week: 13, source: "Day062 교재1", ko: "재료가 기본적으로 버터, 밀가루, 설탕이군. 그래서 맛이 좋은 거구나.", en: "The ingredients are basically just butter, flour, and sugar. No wonder it tastes good." },
        { week: 13, source: "Day062 교재2", ko: "Gerry가 어젯밤에 사장이랑 소주 다섯 병 마셨다더라.", en: "I heard Gerry drank five bottles of soju with the boss last night." },
        { week: 13, source: "Day062 교재2", ko: "아, 그래서 아침에 그 친구 눈이 그렇게 빨갰구나.", en: "Oh, no wonder his eyes were so red this morning." },
        { week: 13, source: "Day062 교재2", ko: "간식 고마워요. 아침 먹고는 아무것도 못 먹었어요.", en: "Thank you for the snack. I didn’t have anything since breakfast." },
        { week: 13, source: "Day062 교재2", ko: "알죠! 그러면 당연히 배고프죠.", en: "I see! No wonder you were so hungry." },
        { week: 13, source: "Day062 교재2", ko: "들어 보니까 은행 직원들은 거의 밤 9시까지 야근을 해야 한대.", en: "I heard some bank workers pretty much have to stick around the office until 9 p.m." },
        { week: 13, source: "Day062 교재2", ko: "그래서 파업을 하는 거구나. 돈을 그렇게 많이 받는데 왜 파업을 하나 했거든.", en: "No wonder they’re on strike. I was wondering, since they get paid so much." },
        { week: 13, source: "Day062 교재3", ko: "타임스퀘어 근처 식당에서 산 이 햄버거 크기 좀 봐. 메뉴에서 봤을 때는 이렇게 큰 줄 몰랐어. 게다가 브레드 스틱도 같이 나오네. 이러니 미국 사람들이 과체중인 게 당연하지.", en: "Look at the size of this hamburger I got from a diner near Times Square. When I saw it on the menu, it didn’t look this big! And it comes with a side of breadsticks. No wonder Americans tend to be overweight." },
        { week: 13, source: "Day062 교재4", ko: "아침으로 시리얼을 먹은 거야? 좀 더 든든한 걸로 먹어야지.", en: "You just had cereal for breakfast? You should have something more substantial than that." },
        { week: 13, source: "Day062 교재4", ko: "아침을 거르는 경우가 대부분입니다.", en: "I skip breakfast, more often than not." },
        { week: 13, source: "Day062 교재4", ko: "오늘 나랑 점심 가볍게 할까?", en: "You wanna grab lunch with me today?" },
        { week: 13, source: "Day062 대표", ko: "어쩐지 기분이 상쾌해 보이더라.", en: "No wonder you look so refreshed." },
        { week: 13, source: "Day063 교재1", ko: "제 상황에 해당하는 딱 맞는 단어가 생각이 안 납니다.", en: "I can’t think of the right word for my situation." },
        { week: 13, source: "Day063 교재1", ko: "‘화가 나’보다 내 감정을 더 잘 표현할 수 있는 단어는 없는 듯해.", en: "I can’t think of a better word to describe how I feel than ‘angry’." },
        { week: 13, source: "Day063 교재1", ko: "전시회 너무 멋졌어. 오후 시간을 이보다 더 잘 보낼 수가 있을까?", en: "What a nice exhibition! I can’t think of a better way to spend my afternoon off." },
        { week: 13, source: "Day063 교재1", ko: "남은 치즈를 어디에다 써야 할지 모르겠네.", en: "I can’t think of a use for all this leftover cheese." },
        { week: 13, source: "Day063 교재1", ko: "듀얼 모니터 쓰면 너무 편리해. 동시에 여러 가지 작업을 하거나 작업을 바꿔 가며 하는 게 가능하거든. 단점은 찾을 수가 없어.", en: "Using dual monitors is really convenient. I can multitask or switch between tasks. I can’t think of any downside." },
        { week: 13, source: "Day063 교재2", ko: "아는 사람 중에 전기차 타는 사람 있어?", en: "Do you know anyone who has an electric vehicle?" },
        { week: 13, source: "Day063 교재2", ko: "당장은 생각나는 사람이 없는데 그래도 한 명은 있을 거야. 자동차 회사랑 딜러들 모두 전기차 홍보에 힘쓰고 있잖아.", en: "I can’t think of anyone at the moment, but I must know at least one. Car makers and dealers are all trying to promote electric vehicles." },
        { week: 13, source: "Day063 교재2", ko: "선생님, 한국어 ‘정’에 해당하는 좋은 번역은 뭘까요?", en: "Sir, what would be a good translation for the Korean term, ‘Jeong’?" },
        { week: 13, source: "Day063 교재2", ko: "네, 그 질문 진짜 많이 받았는데요. 저도 딱 한 단어로는 생각이 안 납니다. affection(애정)? attachment(애착)? 딱 이거다 싶은 게 하나도 없네요.", en: "Yeah, I’ve been getting that question a lot, but I can’t really think of a single good expression. Affection? Attachment? Nothing seems quite right." },
        { week: 13, source: "Day063 교재3", ko: "(사무용품 회사 직원이 같은 회사 타 부서 팀장에게 보내는 이메일)\n조 팀장님께\n잠깐 시간 되시면, 배송 문제 좀 도와주실 수 있을까요? 저희가 어쩌다가 며칠 동안 배송하는 걸 깜박했고요, 배송일을 약속한 것이 목요일인데 그때까지 고객에게 물건을 배송할 방법이 생각나지 않습니다.", en: "Mr. Cho,\nIf you have a moment, I could use your help with a shipping problem. We accidentally forgot to send a package out for several days, and now I can’t think of a way to get it to the customer by Thursday, which is our guaranteed delivery date." },
        { week: 13, source: "Day063 교재4", ko: "A: 이제 구인 공고 올리셨나요?", en: "Have you gotten around to posting that job opening yet?" },
        { week: 13, source: "Day063 교재4", ko: "B: 죄송해요. 정말 깜박했어요.", en: "Oh, I’m sorry. That slipped my mind." },
        { week: 13, source: "Day063 교재4", ko: "잘 기억이 안 나.", en: "I don’t quite remember." },
        { week: 13, source: "Day063 교재4", ko: "나 공과금 안 낸 거 이제 생각났네.", en: "It just occurred to me that I didn’t pay the bill." },
        { week: 13, source: "Day063 교재4", ko: "방금 든 생각인데요. 교사로 일할 때 학생들 대부분이 꿈은 없고 공부에만 전념했던 것 같네요.", en: "It just occurred to me that, when I worked as a teacher, most of my students didn’t have any dreams, and only focused on studying." },
        { week: 13, source: "Day063 대표", ko: "이 말을 어떻게 꺼내야 할지.", en: "I can’t think of the right thing to say." },
        { week: 13, source: "Day064 교재1", ko: "그래서 내가 다른 재즈 페스티벌에 안 가는 거야. 그나저나 넌 재즈 좋아해?", en: "That’s why I’ll never go to another Jazz Festival. Do you like jazz, by the way?" },
        { week: 13, source: "Day064 교재1", ko: "이 방에는 두 개의 트윈 침대가 구비되어 있습니다. 참고로 해변도 너무 잘 보입니다.", en: "The room comes with two twin beds. You’ll also have a great view of the beach, by the way." },
        { week: 13, source: "Day064 교재1", ko: "제 친구가 트레이너를 구하고 있어요. 참고로 제 친구는 싱글이에요.", en: "I have a friend who’s looking for a trainer. He’s single, by the way." },
        { week: 13, source: "Day064 교재1", ko: "Mark랑 Mindy 먹을 음식도 주문해야 해. 그나저나 그 친구들은 언제 도착한대?", en: "We’ll just have to order something for Mark and Mindy. When are they coming, by the way?" },
        { week: 13, source: "Day064 교재2", ko: "나랑 같이 요가 수업 받을래? 친구를 소개하면 할인받을 수 있거든.", en: "Do you want to join this yoga class with me? I can get a discount for referring a friend." },
        { week: 13, source: "Day064 교재2", ko: "생각해 볼게. 유연성을 좀 기르긴 해야 해. 근데 선생님 귀여우셔?", en: "I’ll think about it. I do need to work on my flexibility. By the way, is the instructor cute?" },
        { week: 13, source: "Day064 교재2", ko: "아직 만나는 사람 없지? 내 친구 Samantha 소개해 줄까? 네 또래인 데다 엄청 착해.", en: "You’re still single, right? Can I set you up with my friend, Samantha? She’s your age and really kind." },
        { week: 13, source: "Day064 교재2", ko: "좋아! 그나저나 Samantha MBTI가 뭔지 알아?", en: "Sounds great! By the way, do you know Samantha’s MBTI?" },
        { week: 13, source: "Day064 교재2", ko: "안녕하세요. 벤츠 신모델 정보 좀 알고 싶어서요.", en: "Hi there. I’d like some more information on the new Mercedes model." },
        { week: 13, source: "Day064 교재2", ko: "물론이죠. 전부 말씀드릴게요. 그나저나 지금 타는 차량 종류가 어떤 거세요?", en: "Sure, I can tell you all about it. Which make of car are you currently driving, by the way?" },
        { week: 13, source: "Day064 교재3", ko: "어젯밤에 나랑 놀아 줘서 고마워! 나는 너무 재미있었는데 너도 그랬으면 좋겠어. 그나저나 회사 안 늦었어? 너 택시 타다가 넘어질 뻔해서 좀 걱정되더라고.", en: "Thanks for hanging out with me last night! I had a great time and I hope you felt the same way. Btw, did you make it to work on time? I was a little worried after you almost fell getting into a cab." },
        { week: 13, source: "Day064 교재4", ko: "A: Greg, 비 오니?", en: "Is it raining, Greg?" },
        { week: 13, source: "Day064 교재4", ko: "B: 아니, 그래도 비옷 챙기렴. 비 올지도 모르잖아.", en: "No, but bring a raincoat anyway. It might rain." },
        { week: 13, source: "Day064 교재4", ko: "A: 어디로 2차를 가야 할지 모르겠네. 주변에 내가 제일 좋아하는 바는 벌써 영업이 끝났거든.", en: "I don’t know where a good place would be to keep drinking. My favorite bar around here is already closed." },
        { week: 13, source: "Day064 교재4", ko: "B: 사실, 괜찮아. 어차피 나 지금 집에 가서 자야 하거든.", en: "Actually, it’s okay. It’s about time for me to get home and go to bed anyway." },
        { week: 13, source: "Day064 교재4", ko: "파리 물가가 비싸긴 하지. 그래도 많은 사람들이 파리에서 휴가를 즐기고 싶어 해.", en: "Paris is expensive, but many people would like to vacation there, anyway." },
        { week: 13, source: "Day064 대표", ko: "새해가 코앞이네. 그나저나 너 부모님 댁에 갈 거야?", en: "New Year’s is just around the corner. Are you going to your parent’s house, by the way?" },
        { week: 13, source: "Day065 교재1", ko: "너 남대문 열린 거 아니?", en: "Are you aware your zipper is down?" },
        { week: 13, source: "Day065 교재1", ko: "너 이에 뭐 낀 거 알아?", en: "Are you aware there is something in your teeth?" },
        { week: 13, source: "Day065 교재1", ko: "이 좌석이 예약석인 줄을 몰랐습니다.", en: "I wasn’t aware that this table was reserved." },
        { week: 13, source: "Day065 교재1", ko: "너 아는지 모르겠는데, 화장실 세면대 막혔어.", en: "I don’t know if you’re aware of this, but the bathroom sink is clogged." },
        { week: 13, source: "Day065 교재1", ko: "네가 아는지 모르겠지만, 수지 동생이 많이 아파.", en: "I don’t know if you’re aware of it, but Suzie’s brother has been seriously ill." },
        { week: 13, source: "Day065 교재2", ko: "셔츠 주머니에 얼룩 묻은 거 아세요?", en: "Are you aware that you have a stain on your shirt pocket?" },
        { week: 13, source: "Day065 교재2", ko: "네, 알고 있는데 지금은 어떻게 할 수가 없어요. 여분 셔츠를 사무실에 하나 둬야겠군요.", en: "Yeah, I know, but there’s nothing I can do about it right now. I think I should keep an extra shirt in my office." },
        { week: 13, source: "Day065 교재2", ko: "김 군과의 면접은 생각보다 별로였어.", en: "I wasn’t very impressed with Mr. Kim’s interview." },
        { week: 13, source: "Day065 교재2", ko: "진짜로? 그 친구 배경을 모르나 보네? 해외 유학도 간 적이 없거든.", en: "Oh, really? Aren’t you aware of his background? He’s never studied abroad." },
        { week: 13, source: "Day065 교재2", ko: "저 사실 남자 친구랑 왔는데요.", en: "I’m actually here with my boyfriend." },
        { week: 13, source: "Day065 교재2", ko: "아, 죄송합니다. 일행이 있는 줄은 몰랐네요.", en: "Oh, I’m sorry. I wasn’t aware you were with someone." },
        { week: 13, source: "Day065 교재3", ko: "안녕하세요, 고객님,\n혹시 모르고 계실까 봐 말씀드리자면, 고객님이 선결제한 데이터를 다 쓰셨습니다. 추가 데이터를 구매하기 바랍니다. 그렇지 않으면 10일 자정부터 서비스가 중단됩니다.\nGT 고객 서비스", en: "Dear customer,\nIn case you aren’t aware, you have used up all of your pre-paid data. Please purchase additional data credit. Otherwise, your service will be suspended starting at midnight on the 10th.\nGT Customer Service" },
        { week: 13, source: "Day065 교재4", ko: "지퍼가 열렸네.", en: "Your fly is open." },
        { week: 13, source: "Day065 교재4", ko: "내가 너를 잃는 것 같은 느낌이 들어.", en: "I feel like I’m losing you." },
        { week: 13, source: "Day065 대표", ko: "시간 가는 줄도 몰랐네.", en: "I wasn’t aware of the time." }
    ];

    // 영어회화 난이도 분리
    const convEasy = rawConvData.filter(item => item.source.includes('대표') || item.source.includes('교재1'));
    const convHard = rawConvData.filter(item => !(item.source.includes('대표') || item.source.includes('교재1')));

    // 퀴즈 진행 상태 변수
    let currentQuestions = [];
    let currentIndex = 0;
    let isPhrasalMode = false;
    let starredQuestions = []; 

    function shuffleArray(array) {
        let shuffled = [...array];
        for (let i = shuffled.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
        }
        return shuffled;
    }

    // 선택된 주차에 맞게 필터링
    function filterByWeek(dataArray) {
        if (currentWeekFilter === 'all') {
            return dataArray.filter(item => item.week >= 13 && item.week <= 16);
        }
        return dataArray.filter(item => item.week === currentWeekFilter);
    }

    function startQuiz(mode) {
        let sourceArray = [];
        let titleMode = "";

        if (mode === 'phrasal-easy') { 
            sourceArray = phrasalEasy; isPhrasalMode = true; 
            titleMode = "🟢 구동사 순한맛 퀴즈"; 
        }
        else if (mode === 'phrasal-hard') { 
            sourceArray = phrasalHard; isPhrasalMode = true; 
            titleMode = "🔴 구동사 매운맛 퀴즈"; 
        }
        else if (mode === 'conv-easy') { 
            sourceArray = convEasy; isPhrasalMode = false; 
            titleMode = "💬 영어회화 순한맛 퀴즈"; 
        }
        else if (mode === 'conv-hard') { 
            sourceArray = convHard; isPhrasalMode = false; 
            titleMode = "🔥 영어회화 매운맛 퀴즈"; 
        }

        const filteredData = filterByWeek(sourceArray);

        if (filteredData.length === 0) {
            alert(`선택하신 주차(Week ${currentWeekFilter})에 해당하는 데이터가 아직 없습니다.`);
            return;
        }

        document.getElementById('mode-selection').classList.add('hidden');
        document.getElementById('quiz-area').classList.remove('hidden');
        
        let weekText = currentWeekFilter === 'all' ? " (Week 13~16 누적)" : ` (Week ${currentWeekFilter})`;
        document.getElementById('main-title').innerText = titleMode + weekText; 
        
        starredQuestions = []; 
        // 7문제만 추출 (데이터가 7개 미만이면 전체 추출)
        const qCount = Math.min(filteredData.length, 7);
        currentQuestions = shuffleArray(filteredData).slice(0, qCount);
        currentIndex = 0;
        
        loadQuestion();
    }

    function loadQuestion() {
        document.getElementById('answer-section').classList.add('hidden');
        document.getElementById('btn-next').classList.add('hidden');
        document.getElementById('btn-finish').classList.add('hidden');
        document.getElementById('meaning-info').classList.add('hidden');
        
        const koBox = document.getElementById('ko-box');
        koBox.style.cursor = 'pointer';
        koBox.style.pointerEvents = 'auto';

        const q = currentQuestions[currentIndex];
        document.getElementById('question-counter').innerText = `문제 ${currentIndex + 1} / ${currentQuestions.length}`;
        document.getElementById('ko-text').innerText = q.ko;
        document.getElementById('en-text').innerText = q.en;
        document.getElementById('source-info').innerText = `출처: ${q.source}`;
        
        if(isPhrasalMode && q.meaning) {
            document.getElementById('meaning-info').innerText = q.meaning;
        }

        const starBtn = document.getElementById('btn-star');
        if (starredQuestions.includes(q)) {
            starBtn.classList.add('active');
            starBtn.innerText = "⭐ 어려워요 (저장됨)";
        } else {
            starBtn.classList.remove('active');
            starBtn.innerText = "⭐ 어려워요";
        }
    }

    function showAnswer() {
        const koBox = document.getElementById('ko-box');
        koBox.style.cursor = 'default';
        koBox.style.pointerEvents = 'none';

        document.getElementById('answer-section').classList.remove('hidden');
        
        if(isPhrasalMode && currentQuestions[currentIndex].meaning) {
            document.getElementById('meaning-info').classList.remove('hidden');
        }
        
        if (currentIndex < currentQuestions.length - 1) {
            document.getElementById('btn-next').classList.remove('hidden');
        } else {
            document.getElementById('btn-finish').classList.remove('hidden');
        }
    }

    function toggleStar() {
        const q = currentQuestions[currentIndex];
        const starBtn = document.getElementById('btn-star');
        const index = starredQuestions.indexOf(q);
        
        if (index > -1) {
            starredQuestions.splice(index, 1);
            starBtn.classList.remove('active');
            starBtn.innerText = "⭐ 어려워요";
        } else {
            starredQuestions.push(q);
            starBtn.classList.add('active');
            starBtn.innerText = "⭐ 어려워요 (저장됨)";
        }
    }

    function playTTS() {
        const textToSpeak = currentQuestions[currentIndex].en;
        if ('speechSynthesis' in window) {
            window.speechSynthesis.cancel();
            const utterance = new SpeechSynthesisUtterance(textToSpeak);
            utterance.lang = 'en-US';
            utterance.rate = 0.9; 
            window.speechSynthesis.speak(utterance);
        } else {
            alert('이 브라우저에서는 음성 듣기 기능을 지원하지 않습니다.');
        }
    }

    function nextQuestion() {
        currentIndex++;
        loadQuestion();
    }

    function showReview() {
        document.getElementById('quiz-area').classList.add('hidden');
        document.getElementById('review-area').classList.remove('hidden');
        document.getElementById('main-title').innerText = "결과 및 오답 노트";

        const reviewList = document.getElementById('review-list');
        reviewList.innerHTML = '';

        if (starredQuestions.length === 0) {
            reviewList.innerHTML = `<div class="review-empty">🎉 어려운 문장이 없습니다! 완벽해요! 🎉</div>`;
        } else {
            starredQuestions.forEach((q, idx) => {
                let meaningHtml = (isPhrasalMode && q.meaning) ? `<div style="font-size: 13px; color: #b45309; background: #fef3c7; padding: 4px 8px; border-radius: 4px; display: inline-block; margin-bottom: 5px;">${q.meaning}</div>` : '';
                
                reviewList.innerHTML += `
                    <div class="review-card">
                        <div style="font-size: 12px; color: #94a3b8; margin-bottom: 5px;">${idx + 1}. 출처: ${q.source}</div>
                        ${meaningHtml}
                        <div class="review-ko">${q.ko}</div>
                        <div class="review-en">${q.en}</div>
                    </div>
                `;
            });
        }
    }

    function resetToHome() {
        document.getElementById('review-area').classList.add('hidden');
        document.getElementById('mode-selection').classList.remove('hidden');
        document.getElementById('main-title').innerText = "🚀 스피드 영어 퀴즈";
    }
</script>

</body>
</html>

```
