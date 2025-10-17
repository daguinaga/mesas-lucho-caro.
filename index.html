import React, { useMemo, useState } from "react";
import { motion } from "framer-motion";
import { Search, ListFilter, PartyPopper, Copy, MapPin, Calendar, Upload, Download } from "lucide-react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";

// ==========================
// 🔧 Configuración / Datos
// ==========================
// Reemplaza esta lista por tu lista real. Formato: { name: "Nombre Apellido", table: "#" }
// Consejo: Puedes pegar tu CSV en el panel "Cargar lista (CSV)" más abajo para cargarlo en caliente.
const initialGuests: { name: string; table: string }[] = [
  { name: "Carolina Barrios", table: "1" },
  { name: "Luis Rodríguez", table: "1" },
  { name: "Rafael Rodríguez", table: "2" },
  { name: "María Fernanda", table: "2" },
  { name: "Javier Ugarte", table: "3" },
  { name: "Ana Lucía", table: "3" },
  { name: "Marcelo Wong", table: "4" },
  { name: "Sofía Pérez", table: "4" },
  { name: "Rodrigo Silva", table: "5" },
  { name: "Valeria Torres", table: "5" },
  { name: "Cecilia González", table: "6" },
  { name: "Tomás Herrera", table: "6" },
];

// Normaliza texto para búsquedas (ignora acentos y mayúsculas)
const normalize = (s: string) =>
  s
    .normalize("NFD")
    .replace(/\p{Diacritic}/gu, "")
    .toLowerCase()
    .trim();

export default function SeatingFinder() {
  const [query, setQuery] = useState("");
  const [mode, setMode] = useState<"search" | "list">("search");
  const [guests, setGuests] = useState(initialGuests);
  const [copied, setCopied] = useState<string | null>(null);
  const [csvOpen, setCsvOpen] = useState(false);
  const [csvText, setCsvText] = useState("nombre,mesa\nCarolina Barrios,1\nLuis Rodríguez,1\nRafael Rodríguez,2\nMaría Fernanda,2\nJavier Ugarte,3\nAna Lucía,3\nMarcelo Wong,4\nSofía Pérez,4\nRodrigo Silva,5\nValeria Torres,5\nCecilia González,6\nTomás Herrera,6\n");

  const results = useMemo(() => {
    if (!query) return [] as typeof guests;
    const q = normalize(query);
    return guests.filter((g) => normalize(g.name).includes(q)).sort((a, b) => a.name.localeCompare(b.name));
  }, [query, guests]);

  const grouped = useMemo(() => {
    const map: Record<string, { name: string; table: string }[]> = {};
    for (const g of guests) {
      map[g.table] = map[g.table] || [];
      map[g.table].push(g);
    }
    const tables = Object.keys(map).sort((a, b) => Number(a) - Number(b));
    return tables.map((t) => ({ table: t, people: map[t].sort((a, b) => a.name.localeCompare(b.name)) }));
  }, [guests]);

  const onCopy = async (text: string) => {
    try {
      await navigator.clipboard.writeText(text);
      setCopied(text);
      setTimeout(() => setCopied(null), 1500);
    } catch {
      // ignore
    }
  };

  const parseCSV = () => {
    // Admite columnas con encabezados: nombre, mesa
    // Separador: coma. Ignora líneas vacías.
    // Ejemplo:
    // nombre,mesa\nJuan Pérez,12\nAna Díaz,8
    const lines = csvText.split(/\r?\n/).filter(Boolean);
    if (lines.length <= 1) return;
    const headers = lines[0].split(",").map((h) => normalize(h));
    const nameIdx = headers.findIndex((h) => h.includes("nombre") || h.includes("invitado") || h.includes("guest"));
    const tableIdx = headers.findIndex((h) => h.includes("mesa") || h.includes("table"));
    if (nameIdx === -1 || tableIdx === -1) return;
    const parsed: { name: string; table: string }[] = [];
    for (let i = 1; i < lines.length; i++) {
      const cols = lines[i].split(",");
      const name = cols[nameIdx]?.trim();
      const table = cols[tableIdx]?.trim();
      if (name && table) parsed.push({ name, table });
    }
    if (parsed.length) setGuests(parsed);
  };

  return (
    <div className="min-h-screen w-full bg-gradient-to-b from-sky-50 via-emerald-50 to-amber-50 text-slate-800">
      {/* Header */}
      <header className="max-w-3xl mx-auto px-4 pt-10 pb-6 text-center">
        <motion.h1
          initial={{ opacity: 0, y: 10 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.5 }}
          className="text-3xl sm:text-4xl font-semibold tracking-tight"
        >
          Lucho & Caro 💛
        </motion.h1>
        <motion.p
          initial={{ opacity: 0, y: 10 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.6, delay: 0.1 }}
          className="mt-2 text-sm sm:text-base flex items-center justify-center gap-3 text-slate-600"
        >
          <span className="inline-flex items-center gap-1"><Calendar className="h-4 w-4" /> 18 de octubre de 2025</span>
          <span className="opacity-40">•</span>
          <span className="inline-flex items-center gap-1"><MapPin className="h-4 w-4" /> Casino de Pimentel, Perú</span>
        </motion.p>
        <motion.p
          initial={{ opacity: 0, y: 10 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.6, delay: 0.15 }}
          className="mt-4 text-base sm:text-lg"
        >
          <span className="font-medium">Tu mesa es…</span> Encuéntrala al toque ✨
        </motion.p>

        {/* Toggle */}
        <div className="mt-6 flex items-center justify-center gap-2">
          <Button
            onClick={() => setMode("search")}
            variant={mode === "search" ? "default" : "secondary"}
            className="rounded-2xl"
          >
            <Search className="mr-2 h-4 w-4" /> Buscar por nombre
          </Button>
          <Button
            onClick={() => setMode("list")}
            variant={mode === "list" ? "default" : "secondary"}
            className="rounded-2xl"
          >
            <ListFilter className="mr-2 h-4 w-4" /> Ver lista por mesas
          </Button>
        </div>
      </header>

      {/* Main */}
      <main className="max-w-3xl mx-auto px-4 pb-20">
        {mode === "search" ? (
          <section>
            <Card className="rounded-2xl shadow-md">
              <CardContent className="p-4 sm:p-6">
                <div className="flex items-center gap-3">
                  <Input
                    value={query}
                    onChange={(e) => setQuery(e.target.value)}
                    placeholder="Escribe tu nombre y apellidos…"
                    className="h-11 rounded-xl"
                  />
                  <Button onClick={() => setQuery("")} variant="ghost" className="rounded-xl">Limpiar</Button>
                </div>

                {/* Resultados */}
                {query && (
                  <div className="mt-6 space-y-3">
                    {results.length === 0 && (
                      <p className="text-slate-600 text-sm">
                        No encontramos ese nombre. Revisa ortografía o acércate al <span className="font-medium">personal</span> 💬
                      </p>
                    )}
                    {results.slice(0, 25).map((g, idx) => (
                      <motion.div
                        key={`${g.name}-${idx}`}
                        initial={{ opacity: 0, y: 8 }}
                        animate={{ opacity: 1, y: 0 }}
                        transition={{ duration: 0.25, delay: idx * 0.03 }}
                        className="flex items-center justify-between rounded-xl border p-3 sm:p-4 bg-white/70 backdrop-blur"
                      >
                        <div>
                          <p className="text-sm sm:text-base font-medium">{g.name}</p>
                          <p className="text-slate-600 text-sm flex items-center gap-2"><PartyPopper className="h-4 w-4" /> Tu mesa: <span className="text-lg font-semibold">{g.table}</span></p>
                        </div>
                        <Button
                          variant="outline"
                          className="rounded-xl"
                          onClick={() => onCopy(`${g.name} — Mesa ${g.table}`)}
                        >
                          <Copy className="mr-2 h-4 w-4" /> {copied === `${g.name} — Mesa ${g.table}` ? "¡Copiado!" : "Copiar"}
                        </Button>
                      </motion.div>
                    ))}
                    {results.length > 25 && (
                      <p className="text-xs text-slate-500">Mostrando 25 resultados. Afina tu búsqueda para ver menos.</p>
                    )}
                  </div>
                )}
              </CardContent>
            </Card>
          </section>
        ) : (
          <section className="space-y-4">
            {grouped.map(({ table, people }) => (
              <motion.div key={table} initial={{ opacity: 0, y: 8 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.25 }}>
                <Card className="rounded-2xl shadow-md">
                  <CardContent className="p-4 sm:p-6">
                    <div className="flex items-center justify-between">
                      <h3 className="text-xl font-semibold">Mesa {table}</h3>
                      <Button variant="outline" className="rounded-xl" onClick={() => onCopy(`Mesa ${table}`)}>
                        <Copy className="mr-2 h-4 w-4" /> Copiar mesa
                      </Button>
                    </div>
                    <ul className="mt-3 grid grid-cols-1 sm:grid-cols-2 gap-2">
                      {people.map((p) => (
                        <li key={`${p.name}-${p.table}`} className="text-sm sm:text-base text-slate-700">
                          {p.name}
                        </li>
                      ))}
                    </ul>
                  </CardContent>
                </Card>
              </motion.div>
            ))}
          </section>
        )}

        {/* Panel de carga CSV (opcional) */}
        <section className="mt-10">
          <details className="group">
            <summary className="cursor-pointer select-none text-sm inline-flex items-center gap-2 px-3 py-2 rounded-xl bg-white/60 border hover:bg-white/80 transition">
              <Upload className="h-4 w-4" /> Cargar lista (CSV)
            </summary>
            <div className="mt-4 rounded-2xl border bg-white/70 p-4 space-y-3">
              <p className="text-sm text-slate-600">
                Pega tu CSV con columnas <span className="font-medium">nombre</span> y <span className="font-medium">mesa</span> (separadas por coma). Luego presiona "Actualizar lista".
              </p>
              <textarea
                className="w-full h-40 rounded-xl border p-3 text-sm"
                value={csvText}
                onChange={(e) => setCsvText(e.target.value)}
              />
              <div className="flex items-center gap-3">
                <Button className="rounded-xl" onClick={parseCSV}><Upload className="mr-2 h-4 w-4" /> Actualizar lista</Button>
                <Button
                  variant="outline"
                  className="rounded-xl"
                  onClick={() => {
                    const header = "nombre,mesa\n";
                    const rows = guests.map((g) => `${g.name},${g.table}`).join("\n");
                    const blob = new Blob([header + rows], { type: "text/csv" });
                    const url = URL.createObjectURL(blob);
                    const a = document.createElement("a");
                    a.href = url;
                    a.download = "invitados_mesas.csv";
                    a.click();
                    URL.revokeObjectURL(url);
                  }}
                >
                  <Download className="mr-2 h-4 w-4" /> Descargar CSV actual
                </Button>
              </div>
            </div>
          </details>
        </section>
      </main>

      {/* Footer */}
      <footer className="max-w-3xl mx-auto px-4 pb-10 text-center text-xs text-slate-500">
        ¿No encuentras tu nombre? Acércate al <span className="font-medium">personal</span> y te ayudamos con una sonrisa ☺️
      </footer>
    </div>
  );
}
