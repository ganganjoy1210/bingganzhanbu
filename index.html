<!DOCTYPE html>  
<html lang="zh-CN">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>天机阁 - 占卜系统原型</title>  
    <script src="https://cdn.tailwindcss.com"></script>  
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>  
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>  
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>  
    <style>  
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }  
        .animate-fade-in { animation: fadeIn 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards; }  
    </style>  
</head>  
<body class="bg-slate-950 text-slate-200 min-h-screen overflow-x-hidden">  
    <div id="root"></div>  
  
    <script type="text/babel">  
        const { useState } = React;  
  
        // --- 知识库：塔罗牌 (保留稳定生图技术，回归人文释义) ---  
        const TAROT_DECK = [  
          { id: 0, name: "0. 愚者 (The Fool)", imageUrl: "https://image.pollinations.ai/prompt/The%20Fool%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2000", up: "纯粹的直觉、归零的心态、向未知跃迁", rev: "鲁莽行事、缺乏对现实边界的敬畏", energy: "neutral" },  
          { id: 1, name: "I. 魔术师 (The Magician)", imageUrl: "https://image.pollinations.ai/prompt/The%20Magician%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2001", up: "资源的绝佳调配、意念显化、行动力", rev: "空有才华却未落地、被表象所蒙蔽", energy: "positive" },  
          { id: 2, name: "II. 女祭司 (High Priestess)", imageUrl: "https://image.pollinations.ai/prompt/The%20High%20Priestess%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2002", up: "向内探索、静默的观察、深层的直觉", rev: "抗拒内心的声音、停留在事物表面", energy: "neutral" },  
          { id: 3, name: "III. 皇后 (The Empress)", imageUrl: "https://image.pollinations.ai/prompt/The%20Empress%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2003", up: "无条件的滋养、丰盛的产出、生命的孕育", rev: "令人窒息的控制欲、能量的过度消耗", energy: "positive" },  
          { id: 4, name: "IV. 皇帝 (The Emperor)", imageUrl: "https://image.pollinations.ai/prompt/The%20Emperor%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2004", up: "建立秩序、绝对的掌控、稳固的基石", rev: "刻板僵化、独断专行带来的反噬", energy: "positive" },  
          { id: 5, name: "V. 教皇 (The Hierophant)", imageUrl: "https://image.pollinations.ai/prompt/The%20Hierophant%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2005", up: "遵循传统智慧、寻求专业指引、精神契约", rev: "盲目服从权威、被陈旧的教条束缚", energy: "neutral" },  
          { id: 6, name: "VI. 恋人 (The Lovers)", imageUrl: "https://image.pollinations.ai/prompt/The%20Lovers%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2006", up: "深度的灵魂联结、价值观的共振、重大抉择", rev: "关系的失衡、逃避必须做出的选择", energy: "positive" },  
          { id: 7, name: "VII. 战车 (The Chariot)", imageUrl: "https://image.pollinations.ai/prompt/The%20Chariot%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2007", up: "驾驭矛盾、坚定的意志、在冲突中前行", rev: "情绪或方向失控、受困于内部的拉扯", energy: "positive" },  
          { id: 8, name: "VIII. 力量 (Strength)", imageUrl: "https://image.pollinations.ai/prompt/Strength%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2008", up: "以柔克刚的包容、驯服内心的野兽、持久的耐力", rev: "被本能驱使、自我怀疑带来的软弱", energy: "positive" },  
          { id: 9, name: "IX. 隐士 (The Hermit)", imageUrl: "https://image.pollinations.ai/prompt/The%20Hermit%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2009", up: "主动的孤独、沉淀与反思、寻找内在光源", rev: "画地为牢的孤立、迷失在自我编织的幻境", energy: "neutral" },  
          { id: 10, name: "X. 命运之轮 (Wheel of Fortune)", imageUrl: "https://image.pollinations.ai/prompt/Wheel%20of%20Fortune%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2010", up: "不可抗的周期流转、关键的契机、顺势而为", rev: "抗拒命运的推力、在低谷期逆势挣扎", energy: "neutral" },  
          { id: 11, name: "XI. 正义 (Justice)", imageUrl: "https://image.pollinations.ai/prompt/Justice%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2011", up: "因果的精准清算、客观与理性的天平", rev: "偏见主导决策、逃避应当承担的代价", energy: "neutral" },  
          { id: 12, name: "XII. 倒吊人 (The Hanged Man)", imageUrl: "https://image.pollinations.ai/prompt/The%20Hanged%20Man%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2012", up: "换个视角的顿悟、有价值的暂缓与牺牲", rev: "毫无意义的内耗、被动地被困在原地", energy: "negative" },  
          { id: 13, name: "XIII. 死神 (Death)", imageUrl: "https://image.pollinations.ai/prompt/Death%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2013", up: "旧形态的彻底剥落、不可逆的结束即开始", rev: "执念过深、不愿放手导致腐朽拖累", energy: "negative" },  
          { id: 14, name: "XIV. 节制 (Temperance)", imageUrl: "https://image.pollinations.ai/prompt/Temperance%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2014", up: "跨越极端的调和、能量的缓缓淬炼、长效平衡", rev: "情绪的剧烈摇摆、过度索取打破了生态", energy: "positive" },  
          { id: 15, name: "XV. 恶魔 (The Devil)", imageUrl: "https://image.pollinations.ai/prompt/The%20Devil%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2015", up: "直面欲望的底色、深度的利益绑定、物质的引诱", rev: "斩断病态的羁绊、从长期的上瘾中觉醒", energy: "negative" },  
          { id: 16, name: "XVI. 高塔 (The Tower)", imageUrl: "https://image.pollinations.ai/prompt/The%20Tower%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2016", up: "虚假基石的坍塌、突如其来的剧变与震荡", rev: "死撑着危楼不愿离开、恐惧改变的发生", energy: "negative" },  
          { id: 17, name: "XVII. 星星 (The Star)", imageUrl: "https://image.pollinations.ai/prompt/The%20Star%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2017", up: "风暴后的疗愈、遥远但清晰的指引、宁静的期盼", rev: "失去信念支撑、被眼前的挫折遮蔽了星光", energy: "positive" },  
          { id: 18, name: "XVIII. 月亮 (The Moon)", imageUrl: "https://image.pollinations.ai/prompt/The%20Moon%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2018", up: "深不见底的潜意识、不安的投射、真相被迷雾笼罩", rev: "迷雾渐渐散去、看清了潜伏在暗处的恐惧", energy: "negative" },  
          { id: 19, name: "XIX. 太阳 (The Sun)", imageUrl: "https://image.pollinations.ai/prompt/The%20Sun%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2019", up: "毫无保留的显化、生命力的极致绽放、纯粹的喜悦", rev: "光芒被短暂遮挡、用力过猛导致的虚晃", energy: "positive" },  
          { id: 20, name: "XX. 审判 (Judgement)", imageUrl: "https://image.pollinations.ai/prompt/Judgement%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2020", up: "灵魂深处的召唤、过去的业力结算、浴火重生", rev: "拒绝内心的真实声音、不愿为过去画上句号", energy: "neutral" },  
          { id: 21, name: "XXI. 世界 (The World)", imageUrl: "https://image.pollinations.ai/prompt/The%20World%20tarot%20card,%20mystical%20digital%20art,%20highly%20detailed?width=400&height=600&nologo=true&seed=2021", up: "一段旅程的完美收官、大圆满、格局的彻底打开", rev: "临门一脚的停滞、视野受限无法看到全貌", energy: "positive" }  
        ];  
  
        // --- 知识库：小六壬 (语言重塑：亦师亦友的睿智建议) ---  
        const LIUREN_DECK = {  
          1: { name: "大安", type: "吉", element: "木", desc: "身不动时，属木，青色，东方。", meaning: "这往往意味着当前的事情已经扎下了根。它未必能给你带来刺激的暴涨，但底盘极其稳固，一切都在按部就班地生长。", action: "宜：守住当下的节奏，稳扎稳打，享受这份安稳。忌：心浮气躁，盲目去追求所谓的捷径或风口。" },  
          2: { name: "留连", type: "凶", element: "水", desc: "卒未归时，属水，黑色，北方。", meaning: "仿佛陷入了泥沼，事情的推进感觉充满了粘滞感。这不是因为你不努力，而是周围的羁绊或未结清的旧账在拖拽你。", action: "宜：暂缓脚步，深呼吸，先去理清那些纠缠不清的情绪或遗留问题。忌：强行破局，在冲动和焦虑下做出任何重大决定。" },  
          3: { name: "速喜", type: "吉", element: "火", desc: "人便至时，属火，红色，南方。", meaning: "这是一股明快且炽热的能量。它暗示着事情的转机和好消息正在迅速靠近，时间窗口就在眼前，稍纵即逝。", action: "宜：借着这股势头，利落出手，大胆推进。忌：过度犹豫和自我怀疑，让绝佳的契机从指缝中溜走。" },  
          4: { name: "赤口", type: "凶", element: "金", desc: "官事凶时，属金，白色，西方。", meaning: "空气中弥漫着摩擦的火花。这代表着沟通中容易出现误解、对立，甚至卷入是非之中，人际上的内耗正在加剧。", action: "宜：管好情绪，在交流时多倾听、少反驳，凡事留有余地。忌：意气用事，卷入无谓的口舌之争，白白消耗自身能量。" },  
          5: { name: "小吉", type: "吉", element: "木", desc: "人来喜时，属木，绿色，东方。", meaning: "它如同春日里的微风，不猛烈却带着善意。事情正在向好的方向平稳过渡，你会收获一些预料之外的小确幸。", action: "宜：在平淡中发现微小的契机，顺水推舟，并与周围的人分享这份善意。忌：眼高手低，对当下的结果抱有不切实际的奢望。" },  
          6: { name: "空亡", type: "凶", element: "土", desc: "音信稀时，属土，黄色，中央。", meaning: "如同在迷雾中挥拳，你所投入的期待和精力很可能会落空。这是一段能量处于低谷的真空期，许多事情并不由你掌控。", action: "宜：平静地接受眼前的落差，把注意力收回到自己身上，权当休养生息。忌：不甘心沉没成本，偏执地继续往无底洞里投入资源。" }  
        };  
  
        function App() {  
          const [view, setView] = useState('home');   
          const [tarotCards, setTarotCards] = useState([]);  
          const [isDrawingTarot, setIsDrawingTarot] = useState(false);  
          const [numbers, setNumbers] = useState(['', '', '']);  
          const [liurenResult, setLiurenResult] = useState(null);  
  
          // --- 重构：灵动且深刻的塔罗势能研判 ---  
          const generateTarotSummary = (cards) => {  
            if (cards.length !== 3) return "";  
            const reversedCount = cards.filter(c => c.isReversed).length;  
            const futureCard = cards[2];  
            const isFutureReversed = futureCard.isReversed;  
            let summary = "";  
  
            if (reversedCount === 0) {  
              summary += "牌面流转极其顺畅。过去与当下的势能正在自然交汇，这意味着事情的底层逻辑已经被理顺。你正握着事态的主导权，无需过多质疑，顺着直觉平稳推进即可。";  
            } else if (reversedCount === 1) {  
              summary += "整体的气场流动是平稳的，但在牌阵中隐约有一丝暗流涌动。这意味着大方向无误，但某个你或许已经察觉却刻意回避的盲区，正需要被重新审视和接纳。";  
            } else if (reversedCount === 2) {  
              summary += "牌阵呈现出非常明显的拉扯感。你内在的渴求与外在的限制正在剧烈交锋，继续强行推进只会带来较深的内耗。这通常是一个清晰的信号，提示你需要停下来，重新校准航向。";  
            } else {  
              summary += "这是一个深度的重构时刻。旧有的认知、执念或关系正在经历一场褪壳。虽然过程伴随着失控感与不适，但这也是为你生命中真正的蜕变腾出空间的必经之路。";  
            }  
  
            summary += ` \n\n至于最终的落点【${futureCard.card.name}】，${isFutureReversed ? '逆位的状态暗示着能量需要更长时间的内化' : '正位的气象昭示着特质将会自然显化'}。`;  
              
            if (futureCard.card.energy === 'positive') {  
              summary += isFutureReversed   
                ? "不必急于向外索求结果，先清理内在的患得患失，当时机成熟，一切会水到渠成。"   
                : "建议你放下防御，顺应这股向上的推力，果断去接纳并拥抱即将到来的契机。";  
            } else if (futureCard.card.energy === 'negative') {  
              summary += isFutureReversed   
                ? "直面潜意识里的那些恐惧和不甘吧，这正是打破旧有负面循环的最好时机。"   
                : "请务必保留一份旁观者的清醒，提前斩断那些只会带来过度消耗的羁绊或幻想。";  
            } else {  
              summary += "保持内心的中立与超然，用理智与直觉的双重锚点来应对接下来的起伏。";  
            }  
            return summary;  
          };  
  
          const drawTarotCards = () => {  
            setIsDrawingTarot(true);  
            setTarotCards([]);  
            setTimeout(() => {  
              let deck = [...TAROT_DECK];  
              let drawn = [];  
              const positions = ["过去诱因", "当前处境", "未来趋势"];  
              for (let i = 0; i < 3; i++) {  
                const randomIndex = Math.floor(Math.random() * deck.length);  
                const isReversed = Math.random() > 0.5;  
                drawn.push({  
                  position: positions[i],  
                  card: deck[randomIndex],  
                  isReversed: isReversed  
                });  
                deck.splice(randomIndex, 1);  
              }  
              setTarotCards(drawn);  
              setIsDrawingTarot(false);  
            }, 1200);  
          };  
  
          const calculateLiuren = () => {  
            const num1 = parseInt(numbers[0]);  
            const num2 = parseInt(numbers[1]);  
            const num3 = parseInt(numbers[2]);  
            if (isNaN(num1) || isNaN(num2) || isNaN(num3)) {  
              alert("心不诚则意不达，请重新输入三个有效的数字。");  
              return;  
            }  
            let resultIndex = (num1 + num2 + num3 - 2) % 6;  
            if (resultIndex === 0) resultIndex = 6;  
            if (resultIndex < 0) resultIndex += 6;  
            setLiurenResult(LIUREN_DECK[resultIndex]);  
          };  
  
          const TarotCardImage = ({ card, isReversed }) => {  
            const [imgError, setImgError] = useState(false);  
            const [imgLoaded, setImgLoaded] = useState(false);  
  
            return (  
              <div className={`relative w-48 h-[330px] rounded-xl overflow-hidden shadow-2xl mb-6 border-2 border-slate-700 transition-transform duration-700 bg-slate-900 ${isReversed ? 'rotate-180' : ''}`}>  
                {!imgLoaded && !imgError && (  
                  <div className="absolute inset-0 flex flex-col items-center justify-center p-4">  
                    <div className="w-8 h-8 border-4 border-indigo-500/30 border-t-indigo-500 rounded-full animate-spin mb-4"></div>  
                    <div className="text-indigo-400/70 text-xs tracking-widest uppercase">灵视显化中</div>  
                  </div>  
                )}  
                {!imgError ? (  
                  <img src={card.imageUrl} alt={card.name} onLoad={() => setImgLoaded(true)} onError={() => { setImgError(true); setImgLoaded(true); }} className={`w-full h-full object-cover transition-opacity duration-1000 ${imgLoaded ? 'opacity-100' : 'opacity-0'}`} />  
                ) : (  
                  <div className="w-full h-full flex flex-col items-center justify-center p-4">  
                    <div className="text-slate-700 mb-4 text-5xl">📖</div>  
                    <div className="text-slate-500 text-xs tracking-widest uppercase">感应失败</div>  
                  </div>  
                )}  
              </div>  
            );  
          };  
  
          const renderHome = () => (  
            <div className="flex flex-col items-center justify-center min-h-screen p-6">  
              <div className="text-center mb-12">  
                <h1 className="text-4xl md:text-5xl font-bold mb-4 tracking-wider text-amber-50">天机阁<span className="text-amber-500/50"> | </span>Divination</h1>  
                <p className="text-slate-400 max-w-md mx-auto">选择你的感知通道。西方隐喻，抑或东方数理，皆为内心之镜。</p>  
              </div>  
              <div className="grid md:grid-cols-2 gap-8 w-full max-w-4xl">  
                <button onClick={() => setView('tarot')} className="group flex flex-col items-center p-8 bg-slate-800/50 rounded-3xl border border-slate-700 hover:border-indigo-500 transition-all duration-300">  
                  <div className="text-indigo-400 mb-4 text-5xl">☽</div>  
                  <h2 className="text-2xl font-semibold mb-2">塔罗牌阵</h2>  
                  <p className="text-slate-400 text-sm">抽取三张大阿尔卡纳，洞悉过去、现在与未来。</p>  
                </button>  
                <button onClick={() => setView('liuren')} className="group flex flex-col items-center p-8 bg-slate-800/50 rounded-3xl border border-slate-700 hover:border-emerald-500 transition-all duration-300">  
                  <div className="text-emerald-400 mb-4 text-5xl">☀</div>  
                  <h2 className="text-2xl font-semibold mb-2">小六壬局</h2>  
                  <p className="text-slate-400 text-sm">提供三个随机数字起课，快速测算吉凶气数。</p>  
                </button>  
              </div>  
            </div>  
          );  
  
          const renderTarot = () => (  
            <div className="min-h-screen p-4 md:p-6 max-w-7xl mx-auto flex flex-col">  
              <header className="flex items-center justify-between py-6 border-b border-slate-800 mb-8">  
                <button onClick={() => { setView('home'); setTarotCards([]); }} className="text-slate-400 hover:text-white transition-colors">← 返回枢纽</button>  
                <h2 className="text-xl font-bold text-indigo-300 tracking-widest">塔罗三牌阵</h2>  
                <div className="w-20"></div>  
              </header>  
              <div className="flex-1 flex flex-col items-center">  
                {tarotCards.length === 0 ? (  
                  <div className="flex flex-col items-center justify-center flex-1">  
                    <p className="text-slate-400 mb-8 text-center px-4 leading-relaxed">请在心中沉浸于你的问题。<br/>点击下方，系统将映射出你的潜意识投影。</p>  
                    <button onClick={drawTarotCards} disabled={isDrawingTarot} className="px-8 py-4 bg-indigo-600 hover:bg-indigo-500 text-white rounded-full font-medium transition-all">  
                      {isDrawingTarot ? '正在洗牌与链接...' : '✨ 启阵'}  
                    </button>  
                  </div>  
                ) : (  
                  <div className="w-full animate-fade-in pb-12">  
                    <div className="flex justify-center mb-8">  
                      <button onClick={drawTarotCards} className="px-6 py-2 bg-slate-800 hover:bg-slate-700 text-slate-300 rounded-full text-sm border border-slate-700 transition-colors">↻ 重新启阵</button>  
                    </div>  
                    <div className="flex flex-col lg:flex-row justify-center items-center lg:items-start gap-12 lg:gap-8 mb-12">  
                      {tarotCards.map((item, idx) => (  
                        <div key={idx} className="flex flex-col items-center relative w-full max-w-xs">  
                          <div className="absolute -top-4 bg-slate-900 border border-indigo-500/30 text-indigo-300 text-xs px-4 py-1 rounded-full z-10 font-medium tracking-widest">{item.position}</div>  
                          <TarotCardImage card={item.card} isReversed={item.isReversed} />  
                          <h3 className="text-lg font-bold text-slate-100 mb-1 text-center h-12 flex items-center">{item.card.name}</h3>  
                          <div className={`text-xs mb-4 font-bold tracking-wider ${item.isReversed ? 'text-rose-400' : 'text-emerald-400'}`}>  
                            {item.isReversed ? '逆位 (REVERSED)' : '正位 (UPRIGHT)'}  
                          </div>  
                          <div className="text-slate-300 text-sm leading-relaxed bg-slate-800/40 border border-slate-700/50 p-5 rounded-xl w-full">  
                            <strong className="text-slate-500 block mb-2 text-xs uppercase tracking-widest">深层映射</strong>  
                            {item.isReversed ? item.card.rev : item.card.up}  
                          </div>  
                        </div>  
                      ))}  
                    </div>  
                    <div className="max-w-3xl mx-auto bg-indigo-950/20 border border-indigo-500/20 rounded-3xl p-8 relative overflow-hidden">  
                      <div className="absolute top-0 left-0 w-2 h-full bg-indigo-500/50"></div>  
                      <div className="flex items-center mb-4 text-indigo-300">  
                        <span className="mr-3 text-2xl opacity-50">❝</span>  
                        <h3 className="text-xl font-bold tracking-widest">全局势能研判</h3>  
                      </div>  
                      <p className="text-slate-300 leading-loose text-lg font-serif whitespace-pre-wrap">{generateTarotSummary(tarotCards)}</p>  
                    </div>  
                  </div>  
                )}  
              </div>  
            </div>  
          );  
  
          const renderLiuren = () => (  
            <div className="min-h-screen p-4 md:p-6 max-w-5xl mx-auto flex flex-col">  
              <header className="flex items-center justify-between py-6 border-b border-slate-800 mb-8">  
                <button onClick={() => { setView('home'); setLiurenResult(null); setNumbers(['','','']); }} className="text-slate-400 hover:text-white transition-colors">← 返回枢纽</button>  
                <h2 className="text-xl font-bold text-emerald-400 tracking-widest">小六壬局</h2>  
                <div className="w-20"></div>  
              </header>  
              <div className="flex-1 flex flex-col items-center">  
                {!liurenResult ? (  
                  <div className="w-full max-w-md bg-slate-800/40 border border-slate-700 rounded-3xl p-6 lg:p-8">  
                    <p className="text-slate-400 text-sm mb-8 text-center leading-relaxed">摒除杂念，凭直觉输入三个介于 1-99 之间的数字。<br/>它们将分别锚定“天、地、人”之气机。</p>  
                    <div className="flex justify-between gap-3 mb-8">  
                      {[0, 1, 2].map((idx) => (  
                        <input key={idx} type="number" min="1" max="99" value={numbers[idx]} onChange={(e) => {  
                            const newNums = [...numbers];  
                            newNums[idx] = e.target.value;  
                            setNumbers(newNums);  
                          }} className="w-full bg-slate-900 border border-slate-600 rounded-xl py-4 text-center text-xl text-emerald-300 focus:outline-none focus:border-emerald-500 transition-colors" placeholder="?" />  
                      ))}  
                    </div>  
                    <button onClick={calculateLiuren} className="w-full py-4 bg-emerald-600 hover:bg-emerald-500 text-white rounded-xl font-medium transition-colors">起课推演</button>  
                  </div>  
                ) : (  
                  <div className="w-full animate-fade-in pb-12">  
                     <div className="flex justify-center mb-8">  
                       <button onClick={() => { setLiurenResult(null); setNumbers(['','','']); }} className="px-6 py-2 bg-slate-800 hover:bg-slate-700 text-slate-300 rounded-full text-sm border border-slate-700 transition-colors">↻ 重新起课</button>  
                    </div>  
                    <div className="grid lg:grid-cols-12 gap-6 lg:gap-8">  
                      <div className="lg:col-span-5 bg-slate-800/50 border border-slate-700 rounded-3xl p-8 flex flex-col justify-center items-center text-center">  
                         <div className={`text-6xl font-bold mb-6 ${liurenResult.type === '吉' ? 'text-emerald-400' : 'text-rose-400'}`}>{liurenResult.name}</div>  
                         <div className="flex gap-4">  
                            <span className={`px-5 py-1.5 rounded-full text-sm font-bold tracking-widest ${liurenResult.type === '吉' ? 'bg-emerald-500/20 text-emerald-300' : 'bg-rose-500/20 text-rose-300'}`}>{liurenResult.type}</span>  
                            <span className="px-5 py-1.5 rounded-full text-sm font-bold tracking-widest bg-slate-900 text-slate-300 border border-slate-700">五行 {liurenResult.element}</span>  
                         </div>  
                      </div>  
                      <div className="lg:col-span-7 flex flex-col gap-6">  
                        <div className="bg-slate-900/50 rounded-3xl p-8 border border-slate-700">  
                          <p className="text-slate-400 font-serif italic mb-4">"{liurenResult.desc}"</p>  
                          <p className="text-slate-200 leading-relaxed">{liurenResult.meaning}</p>  
                        </div>  
                        <div className="bg-emerald-950/20 rounded-3xl p-8 border border-emerald-500/20">  
                           <div className="flex items-center mb-4 text-emerald-400">  
                             <span className="mr-3 text-2xl opacity-50">❝</span>  
                             <h3 className="text-lg font-bold tracking-widest">最终行动断语</h3>  
                           </div>  
                           <div className="space-y-4">  
                             {liurenResult.action.split('。').filter(Boolean).map((sentence, idx) => {  
                               const isYi = sentence.includes('宜：');  
                               return (  
                                 <div key={idx} className={`p-4 rounded-xl border ${isYi ? 'bg-emerald-900/30 border-emerald-800/50 text-emerald-200' : 'bg-rose-900/20 border-rose-800/30 text-rose-200'}`}>  
                                   <span className={`font-bold mr-2 ${isYi ? 'text-emerald-400' : 'text-rose-400'}`}>{isYi ? '[ 宜 ]' : '[ 忌 ]'}</span>  
                                   {sentence.replace(/[宜忌]：/, '')}  
                                 </div>  
                               );  
                             })}  
                           </div>  
                        </div>  
                      </div>  
                    </div>  
                  </div>  
                )}  
              </div>  
            </div>  
          );  
  
          return (  
            <div className="min-h-screen font-sans selection:bg-indigo-500/30">  
              {view === 'home' && renderHome()}  
              {view === 'tarot' && renderTarot()}  
              {view === 'liuren' && renderLiuren()}  
            </div>  
          );  
        }  
  
        const root = ReactDOM.createRoot(document.getElementById('root'));  
        root.render(<App />);  
    </script>  
</body>  
</html>  
