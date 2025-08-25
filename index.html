import React, { useEffect, useMemo, useState } from "react";
import { motion, AnimatePresence } from "framer-motion";
import {
  LineChart,
  Line,
  XAxis,
  YAxis,
  CartesianGrid,
  Tooltip,
  ResponsiveContainer,
  RadarChart,
  Radar,
  PolarGrid,
  PolarAngleAxis,
  PolarRadiusAxis,
} from "recharts";
import {
  Trophy,
  BookOpen,
  MessageSquare,
  Settings,
  Swords,
  LogOut,
  User,
  Plus,
  Send,
  TrendingUp,
  BrainCircuit,
} from "lucide-react";

/**
 * AI-Powered Study Hub (Single-file React App)
 * - Lightweight client-side app with localStorage persistence
 * - Features: Auth (nickname), Adaptive Daily Test, Instant Feedback, Skill Radar,
 *             Leaderboard, Forum, Settings.
 * - Stack: React + Tailwind + Framer Motion + Recharts (all pre-wired in this sandbox)
 *
 * Tip: Export this component into a Next.js page or a CRA/Vite project directly.
 */

// -------------------- Utilities --------------------
const todayKey = () => new Date().toISOString().slice(0, 10); // YYYY-MM-DD
const uid = () => Math.random().toString(36).slice(2, 10);

const SUBJECTS = ["Physics", "Chemistry", "Maths"];

// Minimal curated JEE-style question bank (tagged by topic + difficulty)
// Each question: { id, subject, topic, difficulty, q, options:[], answer, explanation }
const BANK = [
  // Physics
  {
    id: "p1",
    subject: "Physics",
    topic: "Kinematics",
    difficulty: 1,
    q: "A particle moves with constant acceleration 2 m/s² from rest. Its velocity after 5 s is?",
    options: ["5 m/s", "10 m/s", "15 m/s", "20 m/s"],
    answer: 1,
    explanation:
      "v = u + at = 0 + 2×5 = 10 m/s.",
  },
  {
    id: "p2",
    subject: "Physics",
    topic: "Work-Energy",
    difficulty: 2,
    q: "A body of mass 2 kg is lifted by 5 m. Change in potential energy? (g=10 m/s²)",
    options: ["50 J", "75 J", "100 J", "125 J"],
    answer: 2,
    explanation: "ΔU = m g h = 2×10×5 = 100 J.",
  },
  {
    id: "p3",
    subject: "Physics",
    topic: "Electrostatics",
    difficulty: 3,
    q: "Two charges +q and +4q are placed 30 cm apart. Where is the net field zero on the line joining them?",
    options: [
      "10 cm from +q",
      "20 cm from +q",
      "Outside, on the +q side",
      "Midpoint",
    ],
    answer: 2,
    explanation:
      "Net E between like charges can't cancel between them (directions same). Cancellation occurs outside, nearer the smaller +q.",
  },
  {
    id: "p4",
    subject: "Physics",
    topic: "Thermodynamics",
    difficulty: 2,
    q: "For an ideal gas in isothermal expansion, which quantity is zero?",
    options: ["ΔU", "Q", "W", "ΔS"],
    answer: 0,
    explanation: "For ideal gas, U depends only on T; isothermal ⇒ ΔU = 0.",
  },
  {
    id: "p5",
    subject: "Physics",
    topic: "Optics",
    difficulty: 2,
    q: "Magnification of a plane mirror is?",
    options: ["+1", "-1", "+2", "0"],
    answer: 0,
    explanation: "Plane mirror forms virtual, erect, same-size image ⇒ m = +1.",
  },
  // Chemistry
  {
    id: "c1",
    subject: "Chemistry",
    topic: "Mole Concept",
    difficulty: 1,
    q: "Number of molecules in 9 g of water? (NA≈6.022×10^23)",
    options: [
      "9/18 × NA",
      "18/9 × NA",
      "(9/18) × 2 × NA",
      "NA",
    ],
    answer: 0,
    explanation: "Moles = 9/18 = 0.5 ⇒ molecules = 0.5 NA.",
  },
  {
    id: "c2",
    subject: "Chemistry",
    topic: "Periodic Table",
    difficulty: 1,
    q: "Which has the highest electronegativity?",
    options: ["F", "O", "N", "Cl"],
    answer: 0,
    explanation: "Fluorine is the most electronegative element.",
  },
  {
    id: "c3",
    subject: "Chemistry",
    topic: "Equilibrium",
    difficulty: 2,
    q: "For the reaction N2 + 3H2 ⇌ 2NH3, increasing pressure shifts equilibrium to?",
    options: ["Left", "Right", "No change", "Depends on catalyst"],
    answer: 1,
    explanation: "Fewer moles on product side ⇒ shifts right with pressure.",
  },
  {
    id: "c4",
    subject: "Chemistry",
    topic: "Organic – SN1/SN2",
    difficulty: 3,
    q: "SN1 is favored by which substrate?",
    options: ["Methyl halide", "Primary", "Secondary", "Tertiary"],
    answer: 3,
    explanation: "Tertiary carbocations are most stable ⇒ SN1 favored.",
  },
  {
    id: "c5",
    subject: "Chemistry",
    topic: "Redox",
    difficulty: 2,
    q: "Oxidation number of S in H2SO4 is?",
    options: ["+2", "+4", "+6", "+8"],
    answer: 2,
    explanation: "2×(+1) + S + 4×(-2) = 0 ⇒ S = +6.",
  },
  // Maths
  {
    id: "m1",
    subject: "Maths",
    topic: "Quadratic Equations",
    difficulty: 1,
    q: "For x²−5x+6=0, sum of roots is?",
    options: ["6", "5", "−5", "−6"],
    answer: 1,
    explanation: "Sum = −b/a = 5.",
  },
  {
    id: "m2",
    subject: "Maths",
    topic: "Calculus – Limits",
    difficulty: 2,
    q: "lim_{x→0} (sin x)/x = ?",
    options: ["0", "1", "sin 1", "Does not exist"],
    answer: 1,
    explanation: "Standard limit equals 1.",
  },
  {
    id: "m3",
    subject: "Maths",
    topic: "Vectors",
    difficulty: 2,
    q: "If |a|=|b|=1 and a·b=0, then |a+b| is?",
    options: ["0", "1", "√2", "2"],
    answer: 2,
    explanation: "Perpendicular unit vectors ⇒ diagonal of square ⇒ √2.",
  },
  {
    id: "m4",
    subject: "Maths",
    topic: "Permutation & Combination",
    difficulty: 3,
    q: "Number of permutations of the word 'BANANA'?",
    options: ["60", "120", "360", "720"],
    answer: 0,
    explanation:
      "6!/(3!2!) = 720/(6×2) = 60.",
  },
  {
    id: "m5",
    subject: "Maths",
    topic: "Coordinate Geometry",
    difficulty: 2,
    q: "Slope of the line 2x − 3y + 6 = 0 is?",
    options: ["2/3", "3/2", "−2/3", "−3/2"],
    answer: 2,
    explanation: "y = (2/3)x + 2 ⇒ slope = 2/3, sign negative when in standard form? No, from rearrangement slope = 2/3. But compare Ax+By+C=0 ⇒ slope = −A/B = −2/−3 = 2/3 ⇒ option −2/3 is incorrect. Correct is 2/3 ⇒ pick option changed to 1?",
  },
];

// Fix the above explanation/options inconsistency for m5:
BANK.find(q => q.id === "m5").options = ["2/3", "3/2", "−2/3", "−3/2"];
BANK.find(q => q.id === "m5").answer = 0;
BANK.find(q => q.id === "m5").explanation = "Slope = −A/B = −2/−3 = 2/3.";

// Topics list derived from BANK
const TOPICS = Array.from(new Set(BANK.map((q) => `${q.subject}:${q.topic}`)));

// -------------------- Storage Layer --------------------
const LS_KEYS = {
  PROFILE: "aihub.profile",
  STATS: "aihub.stats", // per-topic accuracy counters
  LEADERBOARD: "aihub.leaderboard",
  FORUM: "aihub.forum",
};

function load(key, fallback) {
  try {
    const v = JSON.parse(localStorage.getItem(key));
    return v ?? fallback;
  } catch {
    return fallback;
  }
}
function save(key, value) {
  localStorage.setItem(key, JSON.stringify(value));
}

// Stats shape: { [topicKey]: { seen, correct } }
function defaultStats() {
  const s = {};
  TOPICS.forEach((t) => (s[t] = { seen: 0, correct: 0 }));
  return s;
}

// -------------------- Adaptive Engine --------------------
function topicScore(stat) {
  const { seen, correct } = stat;
  if (seen === 0) return 0; // unseen ⇒ prioritize
  return correct / seen;
}

function pickDailyTest(stats, n = 10) {
  // Weight questions by inverse proficiency for their topic
  const topicWeights = {};
  for (const t of TOPICS) {
    topicWeights[t] = 1 - topicScore(stats[t]);
  }
  const pool = [...BANK];

  const picked = [];
  const used = new Set();
  while (picked.length < Math.min(n, pool.length)) {
    // Roulette selection by weight
    const weights = pool.map((q) => topicWeights[`${q.subject}:${q.topic}`] + 0.05 * q.difficulty);
    const sum = weights.reduce((a, b) => a + b, 0) || 1;
    let r = Math.random() * sum;
    let idx = 0;
    for (; idx < pool.length; idx++) {
      r -= weights[idx];
      if (r <= 0) break;
    }
    const q = pool[idx] || pool[pool.length - 1];
    if (!used.has(q.id)) {
      picked.push(q);
      used.add(q.id);
    }
    pool.splice(idx, 1);
  }
  return picked;
}

function evaluate(questions, responses) {
  let correct = 0;
  const details = questions.map((q, i) => {
    const ok = responses[i] === q.answer;
    if (ok) correct++;
    return { id: q.id, ok, correctIndex: q.answer, chosen: responses[i] };
  });
  return { score: correct, total: questions.length, details };
}

// -------------------- UI Components --------------------
function Header({ user, onLogout }) {
  return (
    <div className="flex items-center justify-between p-4 md:p-6 bg-white/70 backdrop-blur border-b sticky top-0 z-50">
      <div className="flex items-center gap-2">
        <BrainCircuit className="w-6 h-6" />
        <h1 className="text-xl md:text-2xl font-bold">AI Study Hub</h1>
        <span className="ml-2 text-xs md:text-sm text-gray-500 hidden sm:block">Adaptive JEE Prep</span>
      </div>
      <div className="flex items-center gap-3">
        <div className="flex items-center gap-2 text-sm bg-gray-100 px-3 py-1 rounded-full">
          <User className="w-4 h-4" />
          <span className="font-medium">{user}</span>
        </div>
        <button onClick={onLogout} className="flex items-center gap-2 px-3 py-2 rounded-xl bg-gray-900 text-white hover:bg-black transition shadow">
          <LogOut className="w-4 h-4" /> Logout
        </button>
      </div>
    </div>
  );
}

function Card({ children, className = "" }) {
  return (
    <div className={`bg-white rounded-2xl shadow-sm p-4 md:p-6 ${className}`}>{children}</div>
  );
}

function StatPill({ label, value }) {
  return (
    <div className="px-3 py-2 rounded-xl bg-gray-100 text-sm flex items-center gap-2">
      <span className="font-medium">{label}</span>
      <span className="text-gray-600">{value}</span>
    </div>
  );
}

function Tabs({ value, onChange, items }) {
  return (
    <div className="flex flex-wrap gap-2">
      {items.map((it) => (
        <button
          key={it.value}
          onClick={() => onChange(it.value)}
          className={`px-4 py-2 rounded-xl border ${
            value === it.value ? "bg-gray-900 text-white" : "bg-white hover:bg-gray-50"
          }`}
        >
          <div className="flex items-center gap-2">
            {it.icon}
            <span className="font-semibold">{it.label}</span>
          </div>
        </button>
      ))}
    </div>
  );
}

function SkillRadar({ stats }) {
  const data = useMemo(() => {
    return TOPICS.map((t) => ({
      topic: t.split(":")[1],
      score: Math.round((topicScore(stats[t]) || 0) * 100),
    }));
  }, [stats]);

  return (
    <div className="w-full h-72">
      <ResponsiveContainer>
        <RadarChart data={data}>
          <PolarGrid />
          <PolarAngleAxis dataKey="topic" />
          <PolarRadiusAxis angle={30} domain={[0, 100]} />
          <Radar name="Proficiency" dataKey="score" fillOpacity={0.4} />
          <Tooltip />
        </RadarChart>
      </ResponsiveContainer>
    </div>
  );
}

function Leaderboard({ data }) {
  return (
    <div className="overflow-x-auto">
      <table className="min-w-full text-left">
        <thead>
          <tr className="text-gray-500 text-sm">
            <th className="p-2">#</th>
            <th className="p-2">User</th>
            <th className="p-2">Score</th>
            <th className="p-2">Date</th>
          </tr>
        </thead>
        <tbody>
          {data.length === 0 && (
            <tr>
              <td colSpan={4} className="p-4 text-gray-500">No entries yet. Be the first! 🚀</td>
            </tr>
          )}
          {data.map((row, i) => (
            <tr key={row.id} className="border-t">
              <td className="p-2">{i + 1}</td>
              <td className="p-2 font-medium">{row.user}</td>
              <td className="p-2">{row.score}/{row.total}</td>
              <td className="p-2 text-sm text-gray-500">{row.date}</td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}

function Forum({ threads, onNewThread, onReply }) {
  const [title, setTitle] = useState("");
  const [body, setBody] = useState("");

  return (
    <div className="space-y-6">
      <Card>
        <div className="flex flex-col md:flex-row gap-3">
          <input
            value={title}
            onChange={(e) => setTitle(e.target.value)}
            className="flex-1 border rounded-xl px-3 py-2"
            placeholder="Start a new discussion (e.g., 'How to memorize inorganic reactions?')"
          />
          <input
            value={body}
            onChange={(e) => setBody(e.target.value)}
            className="flex-[2] border rounded-xl px-3 py-2"
            placeholder="What's on your mind?"
          />
          <button
            onClick={() => {
              if (!title.trim()) return;
              onNewThread({ id: uid(), title: title.trim(), posts: [{ id: uid(), text: body.trim(), ts: Date.now() }] });
              setTitle("");
              setBody("");
            }}
            className="px-4 py-2 rounded-xl bg-gray-900 text-white hover:bg-black flex items-center gap-2"
          >
            <Plus className="w-4 h-4" /> Post
          </button>
        </div>
      </Card>

      <div className="space-y-4">
        {threads.length === 0 && (
          <Card>
            <div className="text-gray-600">No threads yet. Ask the first question! 💬</div>
          </Card>
        )}

        {threads.map((th) => (
          <Card key={th.id}>
            <div className="mb-2">
              <h3 className="text-lg font-semibold">{th.title}</h3>
            </div>
            <div className="space-y-2">
              {th.posts.map((p) => (
                <div key={p.id} className="p-3 bg-gray-50 rounded-xl text-sm flex items-start gap-2">
                  <MessageSquare className="w-4 h-4 mt-0.5" />
                  <div>
                    <div>{p.text || "(no text)"}</div>
                    <div className="text-xs text-gray-500 mt-1">{new Date(p.ts).toLocaleString()}</div>
                  </div>
                </div>
              ))}
            </div>
            <ReplyBox onSend={(text) => onReply(th.id, text)} />
          </Card>
        ))}
      </div>
    </div>
  );
}

function ReplyBox({ onSend }) {
  const [txt, setTxt] = useState("");
  return (
    <div className="mt-3 flex items-center gap-2">
      <input
        value={txt}
        onChange={(e) => setTxt(e.target.value)}
        className="flex-1 border rounded-xl px-3 py-2"
        placeholder="Write a reply..."
      />
      <button
        onClick={() => {
          const t = txt.trim();
          if (!t) return;
          onSend(t);
          setTxt("");
        }}
        className="px-4 py-2 rounded-xl bg-gray-900 text-white hover:bg-black flex items-center gap-2"
      >
        <Send className="w-4 h-4" /> Send
      </button>
    </div>
  );
}

function DailyTest({ stats, onSubmit, todaySeed }) {
  const [questions, setQuestions] = useState([]);
  const [answers, setAnswers] = useState({});
  const [submitted, setSubmitted] = useState(false);
  const [result, setResult] = useState(null);

  useEffect(() => {
    // Create deterministic selection per day by seeding Math.random (simple LCG)
    const seedStr = todaySeed + ":aihub";
    let seed = 0;
    for (let i = 0; i < seedStr.length; i++) seed = (seed * 31 + seedStr.charCodeAt(i)) >>> 0;
    const rand = () => ((seed = (1664525 * seed + 1013904223) >>> 0) / 2 ** 32);

    // copy stats to avoid mutating
    const localStats = JSON.parse(JSON.stringify(stats));

    const topicWeights = {};
    for (const t of TOPICS) topicWeights[t] = 1 - topicScore(localStats[t]);

    const pool = [...BANK];
    const picked = [];
    const used = new Set();
    while (picked.length < Math.min(10, pool.length)) {
      const weights = pool.map((q) => topicWeights[`${q.subject}:${q.topic}`] + 0.05 * q.difficulty);
      const sum = weights.reduce((a, b) => a + b, 0) || 1;
      let r = rand() * sum;
      let idx = 0;
      for (; idx < pool.length; idx++) {
        r -= weights[idx];
        if (r <= 0) break;
      }
      const q = pool[idx] || pool[pool.length - 1];
      if (!used.has(q.id)) {
        picked.push(q);
        used.add(q.id);
      }
      pool.splice(idx, 1);
    }
    setQuestions(picked);
  }, [todaySeed, stats]);

  const answeredCount = Object.keys(answers).length;

  const handleSubmit = () => {
    const ordered = questions.map((_, i) => answers[i]);
    const res = evaluate(questions, ordered);
    setResult(res);
    setSubmitted(true);

    // Update topic stats
    const newStats = JSON.parse(JSON.stringify(stats));
    res.details.forEach((d) => {
      const q = questions.find((qq) => qq.id === d.id);
      const key = `${q.subject}:${q.topic}`;
      newStats[key].seen += 1;
      if (d.ok) newStats[key].correct += 1;
    });
    onSubmit(res, newStats);
  };

  if (submitted && result) {
    return (
      <AnimatePresence>
        <motion.div initial={{ opacity: 0, y: 10 }} animate={{ opacity: 1, y: 0 }} exit={{ opacity: 0 }}>
          <Card>
            <div className="flex items-center justify-between">
              <h3 className="text-xl font-semibold flex items-center gap-2"><Swords className="w-5 h-5" /> Your Daily Test Result</h3>
              <div className="text-sm text-gray-500">{todaySeed}</div>
            </div>
            <div className="mt-4 flex flex-wrap gap-3">
              <StatPill label="Score" value={`${result.score}/${result.total}`} />
              <StatPill label="Accuracy" value={`${Math.round((result.score / result.total) * 100)}%`} />
            </div>

            <div className="mt-6 space-y-3">
              {questions.map((q, i) => (
                <div key={q.id} className="p-3 rounded-xl border">
                  <div className="font-medium">Q{i + 1}. {q.q}</div>
                  <div className="mt-1 text-sm text-gray-500">{q.subject} • {q.topic} • D{q.difficulty}</div>
                  <div className="mt-2 text-sm">
                    Your answer: <span className={result.details[i].ok ? "text-green-600" : "text-red-600"}>{q.options[result.details[i].chosen] ?? "—"}</span> • Correct: <span className="font-medium">{q.options[q.answer]}</span>
                  </div>
                  <div className="mt-1 text-gray-600 text-sm">Explanation: {q.explanation}</div>
                </div>
              ))}
            </div>
          </Card>
        </motion.div>
      </AnimatePresence>
    );
  }

  return (
    <Card>
      <div className="flex items-center justify-between">
        <h3 className="text-xl font-semibold flex items-center gap-2"><BookOpen className="w-5 h-5" /> Daily Adaptive Test</h3>
        <div className="text-sm text-gray-500">{todaySeed}</div>
      </div>
      <div className="mt-4 text-sm text-gray-600">
        Selected to target your weakest topics. Answer all questions to submit.
      </div>

      <div className="mt-6 space-y-5">
        {questions.map((q, i) => (
          <div key={q.id} className="p-4 rounded-2xl border">
            <div className="font-medium">Q{i + 1}. {q.q}</div>
            <div className="mt-1 text-sm text-gray-500">{q.subject} • {q.topic} • D{q.difficulty}</div>
            <div className="mt-3 grid grid-cols-1 md:grid-cols-2 gap-2">
              {q.options.map((opt, idx) => {
                const active = answers[i] === idx;
                return (
                  <button
                    key={idx}
                    onClick={() => setAnswers({ ...answers, [i]: idx })}
                    className={`text-left px-3 py-2 rounded-xl border ${active ? "bg-gray-900 text-white" : "hover:bg-gray-50"}`}
                  >
                    {String.fromCharCode(65 + idx)}. {opt}
                  </button>
                );
              })}
            </div>
          </div>
        ))}
      </div>

      <div className="mt-6 flex items-center justify-between">
        <div className="text-sm text-gray-500">Answered {answeredCount}/{questions.length}</div>
        <button
          onClick={handleSubmit}
          disabled={answeredCount !== questions.length}
          className={`px-5 py-2 rounded-xl flex items-center gap-2 shadow ${
            answeredCount === questions.length ? "bg-gray-900 text-white hover:bg-black" : "bg-gray-200 text-gray-500 cursor-not-allowed"
          }`}
        >
          <Trophy className="w-4 h-4" /> Submit
        </button>
      </div>
    </Card>
  );
}

function Dashboard({ stats, history }) {
  const trend = useMemo(() => {
    // Build simple timeline of last attempts
    return history.slice(-7).map((h) => ({ date: h.date, accuracy: Math.round((h.score / h.total) * 100) }));
  }, [history]);

  return (
    <div className="grid grid-cols-1 lg:grid-cols-5 gap-6">
      <Card className="lg:col-span-3">
        <div className="flex items-center gap-2 mb-2">
          <TrendingUp className="w-5 h-5" />
          <h3 className="text-lg font-semibold">Performance Trend</h3>
        </div>
        <div className="w-full h-64">
          <ResponsiveContainer>
            <LineChart data={trend}>
              <CartesianGrid strokeDasharray="3 3" />
              <XAxis dataKey="date" />
              <YAxis domain={[0, 100]} />
              <Tooltip />
              <Line type="monotone" dataKey="accuracy" />
            </LineChart>
          </ResponsiveContainer>
        </div>
      </Card>

      <Card className="lg:col-span-2">
        <div className="flex items-center gap-2 mb-2">
          <BrainCircuit className="w-5 h-5" />
          <h3 className="text-lg font-semibold">Skill Radar</h3>
        </div>
        <SkillRadar stats={stats} />
      </Card>

      <Card className="lg:col-span-5">
        <div className="text-sm text-gray-600">
          Tip: Your next Daily Test will emphasize topics with lower scores on the radar. Keep grinding! 🔁
        </div>
      </Card>
    </div>
  );
}

export default function App() {
  const [user, setUser] = useState("");
  const [active, setActive] = useState("dashboard");
  const [stats, setStats] = useState(defaultStats());
  const [leaderboard, setLeaderboard] = useState([]);
  const [forum, setForum] = useState([]);
  const [history, setHistory] = useState([]); // attempt history

  // On mount, hydrate from localStorage
  useEffect(() => {
    const profile = load(LS_KEYS.PROFILE, { user: "" });
    if (profile.user) setUser(profile.user);
    setStats(load(LS_KEYS.STATS, defaultStats()));
    setLeaderboard(load(LS_KEYS.LEADERBOARD, []));
    setForum(load(LS_KEYS.FORUM, []));
    setHistory(load("aihub.history", []));
  }, []);

  useEffect(() => save(LS_KEYS.PROFILE, { user }), [user]);
  useEffect(() => save(LS_KEYS.STATS, stats), [stats]);
  useEffect(() => save(LS_KEYS.LEADERBOARD, leaderboard), [leaderboard]);
  useEffect(() => save(LS_KEYS.FORUM, forum), [forum]);
  useEffect(() => save("aihub.history", history), [history]);

  const logout = () => {
    setUser("");
    save(LS_KEYS.PROFILE, { user: "" });
  };

  const today = todayKey();

  const handleSubmitTest = (res, newStats) => {
    setStats(newStats);
    const entry = { id: uid(), user, score: res.score, total: res.total, date: today };
    const newLB = [...leaderboard, entry]
      .sort((a, b) => b.score / b.total - a.score / a.total)
      .slice(0, 20);
    setLeaderboard(newLB);
    setHistory([...history, entry]);
    setActive("dashboard");
  };

  const addThread = (th) => setForum([th, ...forum]);
  const addReply = (threadId, text) => {
    setForum((prev) =>
      prev.map((t) =>
        t.id === threadId ? { ...t, posts: [...t.posts, { id: uid(), text, ts: Date.now() }] } : t
      )
    );
  };

  if (!user) {
    return (
      <div className="min-h-screen bg-gradient-to-b from-gray-50 to-gray-100 flex items-center justify-center p-6">
        <Card className="max-w-xl w-full">
          <div className="text-center">
            <h1 className="text-2xl md:text-3xl font-extrabold">Welcome to AI Study Hub</h1>
            <p className="text-gray-600 mt-2">Adaptive practice • Instant feedback • Community support</p>
          </div>
          <div className="mt-6">
            <label className="text-sm text-gray-600">Enter your nickname</label>
            <input
              className="mt-1 w-full border rounded-xl px-3 py-2"
              placeholder="e.g., Vikrant_Op"
              onKeyDown={(e) => {
                if (e.key === "Enter") {
                  const v = e.currentTarget.value.trim();
                  if (v) setUser(v);
                }
              }}
            />
            <button
              onClick={() => {
                const el = document.querySelector("input[placeholder='e.g., Vikrant_Op']");
                const v = el?.value.trim();
                if (v) setUser(v);
              }}
              className="mt-3 w-full px-4 py-2 rounded-xl bg-gray-900 text-white hover:bg-black"
            >
              Enter
            </button>
          </div>
          <div className="mt-4 text-xs text-gray-500">Your data is stored locally in your browser.</div>
        </Card>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-gradient-to-b from-white to-gray-50">
      <Header user={user} onLogout={logout} />

      <main className="max-w-6xl mx-auto p-4 md:p-6 space-y-6">
        <div className="flex flex-col md:flex-row md:items-center md:justify-between gap-3">
          <Tabs
            value={active}
            onChange={setActive}
            items={[
              { value: "dashboard", label: "Dashboard", icon: <TrendingUp className="w-4 h-4" /> },
              { value: "test", label: "Daily Test", icon: <BookOpen className="w-4 h-4" /> },
              { value: "leaderboard", label: "Leaderboard", icon: <Trophy className="w-4 h-4" /> },
              { value: "forum", label: "Forum", icon: <MessageSquare className="w-4 h-4" /> },
              { value: "settings", label: "Settings", icon: <Settings className="w-4 h-4" /> },
            ]}
          />
          <div className="text-sm text-gray-500">Date: {today}</div>
        </div>

        {active === "dashboard" && <Dashboard stats={stats} history={history} />}

        {active === "test" && (
          <DailyTest stats={stats} onSubmit={handleSubmitTest} todaySeed={today} />
        )}

        {active === "leaderboard" && (
          <Card>
            <h3 className="text-lg font-semibold mb-3 flex items-center gap-2"><Trophy className="w-5 h-5" /> Global Leaderboard (Local)</h3>
            <Leaderboard data={leaderboard} />
          </Card>
        )}

        {active === "forum" && (
          <Forum threads={forum} onNewThread={addThread} onReply={addReply} />
        )}

        {active === "settings" && (
          <Card>
            <h3 className="text-lg font-semibold mb-4">Settings</h3>
            <div className="space-y-4">
              <button
                onClick={() => {
                  if (!confirm("Reset all progress? This clears stats, history, leaderboard, and forum.")) return;
                  setStats(defaultStats());
                  setLeaderboard([]);
                  setForum([]);
                  setHistory([]);
                }}
                className="px-4 py-2 rounded-xl bg-gray-900 text-white hover:bg-black"
              >
                Reset All Data
              </button>
              <div className="text-sm text-gray-500">All data is stored locally in your browser. For multi-device sync, connect a backend later (Supabase/Firebase/Express + Postgres).</div>
            </div>
          </Card>
        )}
      </main>

      <footer className="max-w-6xl mx-auto p-6 text-xs text-gray-500">
        © {new Date().getFullYear()} AI Study Hub • Built for focused, adaptive JEE prep.
      </footer>
    </div>
  );
}
