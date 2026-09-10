import { Play, Pause, RotateCcw, Zap, Users, Trash2, Route } from 'lucide-react';

interface ControlPanelProps {
  isRunning: boolean;
  onStart: () => void;
  onPause: () => void;
  onReset: () => void;
  onAddSuddenObstacle: () => void;
  onAddRandomTraffic: () => void;
  onClearObstacles: () => void;
  onRecalculatePath: () => void;
}

function ControlButton({
  onClick,
  label,
  icon: Icon,
  variant = 'default',
}: {
  onClick: () => void;
  label: string;
  icon: typeof Play;
  variant?: 'default' | 'primary' | 'danger' | 'warning' | 'accent';
}) {
  const variants: Record<string, string> = {
    default: 'bg-slate-800 hover:bg-slate-700 border-slate-600 text-slate-200',
    primary: 'bg-emerald-900/60 hover:bg-emerald-800 border-emerald-600 text-emerald-300',
    danger: 'bg-red-900/60 hover:bg-red-800 border-red-600 text-red-300',
    warning: 'bg-amber-900/60 hover:bg-amber-800 border-amber-600 text-amber-300',
    accent: 'bg-cyan-900/60 hover:bg-cyan-800 border-cyan-600 text-cyan-300',
  };

  return (
    <button
      onClick={onClick}
      className={`flex items-center gap-2 px-3 py-2 rounded-lg border text-sm font-medium transition-all duration-200 active:scale-95 ${variants[variant]}`}
    >
      <Icon size={16} />
      <span className="hidden sm:inline">{label}</span>
    </button>
  );
}

export default function ControlPanel({
  isRunning,
  onStart,
  onPause,
  onReset,
  onAddSuddenObstacle,
  onAddRandomTraffic,
  onClearObstacles,
  onRecalculatePath,
}: ControlPanelProps) {
  return (
    <div className="flex flex-wrap gap-2">
      {isRunning ? (
        <ControlButton onClick={onPause} label="Pause" icon={Pause} variant="warning" />
      ) : (
        <ControlButton onClick={onStart} label="Start" icon={Play} variant="primary" />
      )}
      <ControlButton onClick={onReset} label="Reset" icon={RotateCcw} />
      <ControlButton
        onClick={onAddSuddenObstacle}
        label="Add Sudden Obstacle"
        icon={Zap}
        variant="danger"
      />
      <ControlButton
        onClick={onAddRandomTraffic}
        label="Random Traffic"
        icon={Users}
        variant="accent"
      />
      <ControlButton
        onClick={onRecalculatePath}
        label="Recalculate"
        icon={Route}
        variant="accent"
      />
      <ControlButton
        onClick={onClearObstacles}
        label="Clear Obstacles"
        icon={Trash2}
        variant="danger"
      />
    </div>
  );
}
